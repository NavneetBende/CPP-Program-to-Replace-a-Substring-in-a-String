Replacing a substring in a string.
In this article, we will learn how to code a C++ program to replace a substring in a string. Replacing a substring with a string means replacing a part of the string with another string. In this program, we will make a function that will first find the substring to be replaced using a for  loop. And then we will replace that substring with the string that we want to replace with using another for loop. At last, we will make the main function and take all the input from the user and then we can print the result.

Replace a Substring in a String Cpp
Algorithm
Accept the inputs.
Create a function
Find the substring in the main string.
Replace it with the new string.
Create main function and call the created function here.
Print result.
 
While loop in C
C++ programming code for replacing a substring in a string
//Replace a Substring in a String
#include<iostream.h> 
#include<string.h> 
using namespace std;
void replaceSubstring(char st[],char sub[],char new_str[])//Function to replace substring.
{
    int stLen,subLen,newLen;
    int i=0,j,k;
    int flag=0,start,end;
    stLen=strlen(st);
    subLen=strlen(sub);
    newLen=strlen(new_str);
    for(i=0;i<stLen;i++)//Finding substring.
    {
        flag=0;
        start=i;
        for(j=0;st[i]==sub[j];j++,i++)
            if(j==subLen-1)
                flag=1;
        end=i;
        if(flag==0)
            i-=j;
        else
        {
            for(j=start;j<end;j++)
            {
                for(k=start;k<stLen;k++)
                    st[k]=st[k+1];
                stLen--;
                i--;
            }
            for(j=start;j<start+newLen;j++)//Replacing suv string with the input string           
             {                
               for(k=stLen;k>=j;k--)
                    st[k+1]=st[k];
                st[j]=new_str[j-start];
                stLen++;
                i++;
            }
        }
    }
}
//Main function.
int main() 
{
    char st[100] = "prepinsta",sub[100] = "insta",new_str[100]="ster ";
    
    replaceSubstring(st,sub,new_str); //Calling created function.
    //Printing result using called function.
    cout<<"The string after replacing substring: "<<st<<endl;
    return 0;
}
Output
The string after replacing substring: prepster 
