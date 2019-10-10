package sample;
import java.util.Stack;

public class ReverseStack {
    static Stack<Character> st = new Stack<>();
    static void insertAtBottom(char x){
        if(st.isEmpty()){
            st.push(x);
        }
        else{
            char q = st.peek();
            st.pop();
            insertAtBottom(x);
            st.push(q);
        }
    }
    static void reverse(){
        if(st.size() > 0){
            char x = st.peek();
            st.pop();
            reverse();
            insertAtBottom(x);
        }
    }
    public static void main(String[] args) {
        st.push('A');
        st.push('B');
        st.push('C');
        st.push('D');
        st.push('E');

        System.out.println("Original stack:");
        System.out.println(st);

        reverse();

        System.out.println("Reversed stack:");
        System.out.println(st);
    }
}
