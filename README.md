 # qinyubing0
 # the Labyrinth design by python
 # the Labyrinth design by python
 # input
 # for example
 # 3 3
 # 0,1 0,2;0,0 1,0;0,1 1,1;0,2 1,2;1,0 1,1;1,1 1,2;1,1 2,1;1,2 2,2;2,0 2,1 
 command= input("Please intput the size and connectivity definition of the labyrinth：")
 # Check the validity of the input
 h=[int(0)]*(int((len(command)+1)/2))
 for i in range(0,len(command),2):
     h[int(i/2)]=int(command[i])
 if 'h' not in vars():
     print("Invalid number format.")
     
 for i in range(len(h)): 
      if h[i]<0:
         print("Number out of range.")
         
 if type(command)!=str:
     print("Incorrect command format.")
     
 for i in range(int((len(h)-2)/4)):
    if h[4*i+2]-h[4*i+4]!=0 and h[4*i+3]-h[4*i+5]!=0:
        print("Maze format error.")
 # Render the labyrinth as a string
 m=command[0]
 m1=int(m)
 n=command[2]
 n1=int(n)
 a=2*m1+1
 b=2*n1+1
 i=len(command)
 j=(i-4+1)/8
 k=int(j)
 l=[int(0)]*4*k
 for x in range(0,k):
    l[4*x+0]=int(command[4+8*x])
    l[4*x+0]=l[4*x+0]*2+1
    l[4*x+1]=int(command[6+8*x])
    l[4*x+1]=l[4*x+1]*2+1
    l[4*x+2]=int(command[8+8*x])
    l[4*x+2]=l[4*x+2]*2+1
    l[4*x+3]=int(command[10+8*x])
    l[4*x+3]=l[4*x+3]*2+1

 output=['W']*a
 print(output)
 for i in range(len(output)):
     output[i]=['W']*b
 q=2*k
 for y in range(0,q):
     output[l[2*y]][l[2*y+1]]='R'

 w=[int(0)]*2*k
 for z in range(0,k):
     w[2*z]=int((l[0+4*z]+l[2+4*z])/2)
     w[2*z+1]=int((l[1+4*z]+l[3+4*z])/2)
 for p in range(0,k):
     output[w[2*p]][w[2*p+1]]='R'
 print(output)
 # If it is the test case input, the output is:
 # [['W', 'W', 'W', 'W', 'W', 'W', 'W'],
 # ['W', 'R', 'W', 'R', 'R', 'R', 'W'],
 # ['W', 'R', 'W', 'R', 'W', 'R', 'W'],
 # ['W', 'R', 'R', 'R', 'R', 'R', 'W'],
 # ['W', 'W', 'W', 'R', 'W', 'R', 'W'],
 # ['W', 'R', 'R', 'R', 'W', 'R', 'W'],
 # ['W', 'W', 'W', 'W', 'W', 'W', 'W']]
