# DSL-6
# Practical No: 06
# Problem Statement: Write a Python program to store first year percentage of students in array. Write function for sorting array of floating point numbers in ascending order using quick sort and display top five scores.
# Program:-
def accept(a):
   n=int(input("Enter no. of Records want's to enter : "))
   for i in range(n):
      x=float(input("enter percentage  of Student %d : "%(i+1)))
      a.append(x)
   print("....Records added sucessfully ....")

def display(a):
   n=len(a)
   if n==0:
      print("....Zero Records....")
   else:
      for i in a:
        print(i,end=' ')
         
def partition(a,start,end):
   pivot=a[start]
   i=start+1
   j=end
   while True:
      while(i<=j and a[i] <= pivot):
         i=i+1
      while(i<=j and a[j]>=pivot):
         j=j-1
      if(i<=j):
        a[i],a[j]=a[j],a[i]
      else:
        break
   a[start],a[j]=a[j],a[start]
   return j
 
def quicksort(a,start,end):
    if(start<end):
       mid=partition(a,start,end)
       quicksort(a,start,mid-1)
       quicksort(a,mid+1,end)

def main():
   a=[]

   while True:
      print("\n")
      print("1:Accept and Display the Records ")
      print("2:Quicksort the Array and Top 5 Students")
      print("3:exit")
      ch=int(input("Enter the choice : "))
      if ch==3:
         break
      elif ch==1:
         accept(a)
         display(a)
      elif ch==2:
         print("\nBefor Quick Sort ")
         display(a)
         print("\n\nAfter Performing Quick Sort")
         n=len(a)
         quicksort(a,0,n-1)
         display(a)
         
         if(n>=5):
            print("\n\nTop 5 Student :")
            for i in range(-1,-5,-1):
               print(a[i])
         else:
            print("\n\nTop %d Student :"%n)
            for i in range(n-1,-1,-1):
               print(a[i])         
      else :
        print("invalid chooice try again !!!!")
main()
# output:
# 1:Accept and Display the Records 
# 2:Quicksort the Array and Top 5 Students
# 3:exit
# Enter the choice : 1
# Enter no. of Records want's to enter : 7
# enter percentage  of Student 1 : 77.89
# enter percentage  of Student 2 : 89.5
# enter percentage  of Student 3 : 90.05
# enter percentage  of Student 4 : 73.77
# enter percentage  of Student 5 : 66.90
# enter percentage  of Student 6 : 87.66
# enter percentage  of Student 7 : 69.69
# ....Records added sucessfully ....
# 77.89 89.5 90.05 73.77 66.9 87.66 69.69

# 1:Accept and Display the Records
# 2:Quicksort the Array and Top 5 Students
# 3:exit
# Enter the choice : 2

# Befor Quick Sort
# 77.89 89.5 90.05 73.77 66.9 87.66 69.69

# After Performing Quick Sort
# 66.9 69.69 73.77 77.89 87.66 89.5 90.05

# Top 5 Student :
# 90.05
# 89.5
# 87.66
# 77.89
