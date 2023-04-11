#include <iostream>
#include <stack>
#include <string>
#include "header.h"

using namespace std;
//characters that can be used 
bool isOperand(char ch) {
    return (ch >= '0' && ch <= '9');
}

//characters that can be used 
bool isOperator(char ch) {
    return (ch == '+' || ch == '-' || ch == '*' || ch == '/' || ch == '%');
}




// i used a string to use use the conversion from infix to postfix 
 string infixToPostfix(string exp) {
    stack<char> st;
    string postfixExp = "";
    for (int i = 0; i < exp.length(); i++) {
        char ch = exp[i];
        if (isOperand(ch)) {
            postfixExp += ch;
        } else if (isOperator(ch)) {
            while (!st.empty() && st.top() != '(' && precedence(ch) <= precedence(st.top())) {
                postfixExp += st.top();
                st.pop();
            }
            st.push(ch);
        } else if (ch == '(') { //error will occur
            st.push(ch);
        } else if (ch == ')') {
            while (!st.empty() && st.top() != '(') { //error will occur 
                postfixExp += st.top();
                st.pop();
            }
            if (!st.empty() && st.top() == '(') { //error will occur
                st.pop();
            } else {
                return "Invalid Expression";
            }
        }
    }
    while (!st.empty()) {
        if (st.top() == '(' || st.top() == ')') {
            return "Invalid Expression"; //error message will appear 
        }
        postfixExp += st.top();
        st.pop();
    }
    return postfixExp;
}

//to see if the expression is okay to use 
bool isBalanced(string exp) {
    stack<char> st;
    for (int i = 0; i < exp.length(); i++) {
        char ch = exp[i];
        if (ch == '{' || ch == '[' || ch == '(') {
            st.push(ch);
        } else if (ch == '}' || ch == ']' || ch == ')') {
            if (st.empty()) {
                return false;
            }
            if ((ch == '}' && st.top() == '{') || (ch == ']' && st.top() == '[') || (ch == ')' && st.top() == '(')) {
                st.pop();
            } else {
                return false;
            }
        }
    }
    return st.empty();
} 

//all the outputs given to user along with the error message 

int main() {
    string infixExp;
    cout << "Enter infix expression: ";
    getline(cin, infixExp);
    if (!isBalanced(infixExp)) {
        cout << "Invalid Expression" << endl;
    } else {
        string postfixExp = infixToPostfix(infixExp);
        cout << "Postfix expression: " << postfixExp << endl;
    }
    return 0;
}
