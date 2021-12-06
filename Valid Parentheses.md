 Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

problem link: https://leetcode.com/problems/valid-parentheses/

### My solution: Using stack it is easy to solve. 
```
bool isValid(string s) {
    stack<char>st;
    if(s.length()>0){
        st.push(s[0]);
    }
    for(int i=1;i<s.length();i++){
        
        char fontChar = '\0';
        if(!st.empty()){
         fontChar = st.top();
        }
        if(fontChar == '(' && s[i]==')'){
            st.pop();
        }else if (fontChar == '{' && s[i] == '}'){
            st.pop();
        }else if (fontChar == '[' && s[i] == ']'){
            st.pop();
        }else{
            st.push(s[i]);
        }
    }
    
    if(st.empty()){
        
        return  true;
    }
    
    return  false;
}
```
