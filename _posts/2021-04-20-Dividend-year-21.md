import pandas as pd    
from urllib.request import urlopen   
from bs4 import BeautifulSoup    

url='https://finance.naver.com/sise/dividend_list.nhn?&page=25'
with urlopen(url) as doc:
    #html = BeautifulSoup(doc, 'lxml')
    #doc=req.urlopen(url).read().decode('euc-kr')
    html = BeautifulSoup(doc,'lxml') 
    div = html.find('td', class_='pgLL')
    print(div.a['href'])
    
s = str(div.a['href']).split('=')
last_page = s[-1]


df = pd.DataFrame()
sise_url = 'https://finance.naver.com/sise/dividend_list.nhn?'  
for page in range(1, int(last_page)+1): 
    page_url = '{}&page={}'.format(sise_url, page)  
    df = df.append(pd.read_html(page_url,encoding='euc-kr',header=0)[0])
    df = df.dropna()
