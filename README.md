# DSA
Check out for the bugs in the DSA questions added .You are also free to add good DSA questions . I will merge them all if I find them suitable .
// C++ program to check for balanced brackets.

#include <bits/stdc++.h>
using namespace std;

    //Function to check if brackets are balanced or not.
    unordered_map<char,int> symbols = {{'[',-1},{'{',-2},{'(',-3},{']',1},{'}',2},{')',3}};
    bool areBracketsBalanced(string x)
    {
        // code 
        stack<char> st;
        for(char bracket:x)
        {
            if(symbols[bracket]<0)
            {
                st.push(bracket);
            }
            else
            {
                if(st.empty())
                return false;
                char top=st.top();
                st.pop();
                if(symbols[top]+symbols[bracket]!=0)
                return false;
            }
        }
        if(st.empty()) return true;
        return false;
    }

// Driver code
int main()
{
	string expr = "{()}[()]";

	// Function call
	if (areBracketsBalanced(expr))
		cout << "Balanced";
	else
		cout << "Not Balanced";
	return 0;
}

// output 
Balanced

// complexities
Time complexity = O(N)
Space complexity = O(N) for stack
