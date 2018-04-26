#include<iostream>
#include<vector>
using namespace std;

class UI
{
 string x,message;
 char n;
 vector <char> c;
 vector <string> m;
 int k;
 public:
 //details
     void setKey() {
          cout<<"Enter key ";
          cin>>k;
     }
     
 
 //1.set messages
      void setMsgs() {
      
       cin.clear();
       cin.ignore(1024, '\n');
	   
	   cout<<"\nEnter the message ";
       getline(cin, message);
       x=message;
       m.push_back(x);  
       
	   cout<<"\nEnter encryption or decryption (e or d) ";
       cin>>n;
       c.push_back(n);
             
       }
  
      
 //2.return encryption or decryption nd msg nd key
 
      vector<string> getMsg() {          
          return m; 
      }
      
      vector<char> getMethod() {
        return c;             
      }
      
      int getKey() {
        return k;    
      }
 //3.display output
      
      void output(string s) {
      	cout<<"\n"<<s;
	  }
};


class ceaserCipher 
{
	 string str;
      int l,t,i,e,key;
      char c;
     vector<string> msg;
     vector<char> ch;
public:
//set message and key
    void setM(vector<string> m, vector<char> c)
    {
     msg = m;
     ch = c;    
     }

    void setKey(int k){
     key = k;
     } 
     
//Encrypt
    void encrypt(string s)
    {
         l=s.length();
         for(i=0;i<l;i++) {
         //lower case
		 if(s[i]>='a' && s[i] <='z') {
             t=s[i];
			 e=((t-97)+key)%26;
			 c=e+97;
			 s[i]=c;  			          
         }
         
		 //upper casse
         if(s[i]>='A' && s[i]<='Z') {
         	t=s[i];
         	e = ((t-65)+key)%26;
         	c = e+65;
         	s[i]=c;	
		 }
		 
		 //numbers
		 if(s[i]>=48 && s[i]<=57) {
		 	t=s[i];
		 	e=((t-48)+key)%10;
		 	c=e+48;
		 	s[i]=c;
		 }
		 //all other cases remains same       
         }
         str = s;
     }

    
//Decrypt
    void decrypt(string s)
    {
         l=s.length();
         for(i=0;i<l;i++) {
         //lower case
		 if(s[i]>='a' && s[i] <='z') {
             t=s[i];
			 e=((t-97)-key);
			 
			 while(e<0) {
				e=26 + e ;
			 }
			 c=e+97;
			 s[i]=c;  			          
         }
         
		 //upper casse
         if(s[i]>='A' && s[i]<='Z') {
         	t=s[i];
         	e = (t-65)-key;
         	while(e<0) {
         	e = 26+e ; 	
			 } 
         	c = e+65;
         	s[i]=c;	
		 }
		 
		 //numbers
		 if(s[i]>=48 && s[i]<=57) {
		 	t=s[i];
		 	key=key%10;
		 	e=(t-48)-key;
		 	e<0? e=10+e : e=e;
		 	c=e+48;
		 	s[i]=c;
		 }
		 //all other cases remains same       
         }
         str = s;
     }

//get Result
    string getMessage() {
    	return str;
    }
      
}; 

int main()
{
	char ch,t;
	string m,s;
	vector <string> message;
	vector<char> type;
	int key,i=0,count=0;
	
	UI ob;
    ceaserCipher cC;
     
    do{
    ob.setMsgs();
    ob.setKey();
   
        
    message = ob.getMsg();
    type = ob.getMethod();
    key = ob.getKey();
    
    
    cC.setM(message,type);
    cC.setKey(key);
    
    	
    m=message[i];
    t=type[i];
    
	if(t== 'e') {
    	cC.encrypt(m);
	} else {
		cC.decrypt(m);		
	}
	
	
    	s=cC.getMessage();
    	ob.output(s);
    	i++;
    	
    cout<<"\nDo you want to continue? y/n";
    cin>>ch;
  
    } while(ch == 'y' || ch =='Y');

        	
}
