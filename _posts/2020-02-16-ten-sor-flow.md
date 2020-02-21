pm 9:03 SUN, 2020-02-16     
 가상환경 로츠카츠AI머신러닝       
 To see if the conda installation of Python is in your PATH variable:    
   On macOS and Linux, open the terminal and run echo $PATH.   
   On Windows, open an Anaconda Prompt and run echo %PATH%             
          
 To see which Python installation is currently set as the default:    
On Windows, open an Anaconda Prompt and run where python.   

(base) C:\Users\Kslee5838>python --versionpython --version   
	python 3.7.3   
(base) C:\Users\Kslee5838>python --versionconda info --envs    

(tensorflow) c:\Users\Kslee5838> python --version  
	3.5.6 ; Anaconda    

⦁ pip install --upgrade tensorflow-gpu   

⦁ import tensorflow as tf     
hello=tf.constant('Hello Tensorflow'quit    
sess=tf.Session()   
print(sess.run(hello))   

⦁ See https://www.tensorflow.org/install/errors           
#??           
당초 tensorflow = 2.0 설치       
그리고 tensorflow gpu 는 뭔지, 일단 tensorflow는 삭제 했음  

커맨드라인에서
git clone https://... .git 입력 

워킹디렉토리  
>>>import os   
>>>os.getcwd()   
>>>print(os.listdur(os.getcwd()))   
   
>>>import sys   
>>>sys.path      
