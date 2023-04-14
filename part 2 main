#include <iostream>
#include "header.h"


using namespace std;

//i put a class for queue putting all the functions in here 
class Queue {
    private:
        int arr[MAX_SIZE]; 
        int front;          
        int rear;           
        int size;         
        
    public:
        Queue() {
            front = rear = -1;  // queue goes to -1 
            size = 0;           // queue is at zero right now 
        }
        
        // inserts new element at the rear
        void enqueue(int element) {
            if (size == MAX_SIZE) {
                cout << "Queue is full. Cannot insert more elements." << endl;
                return;
            }
            
            if (front == -1) {
                front++;
            }
            
            rear++;
            arr[rear] = element;
            size++;
        }
        
        // removes the first element and returns it 
        int dequeue() {
            if (front == -1 || front > rear) {
                cout << "Queue is empty. Cannot dequeue elements." << endl;
                return -1;
            }
            
            int element = arr[front];
            front++;
            size--;
            
            return element;
        }
        
        // returns the front element in the queue without removing it
        int peek() {
            if (front == -1 || front > rear) {
                cout << "Queue is empty. Cannot peek elements." << endl;
                return -1;
            }
            
            return arr[front];
        }
        
        // checks to see if the queue is empty 
        bool isEmpty() {
            return (front == -1 || front > rear);
        }
        
        // shows the total number of elements in queue
        int getSize() {
            return size;
        }
};


//main function compiling everything 
int main() {
    Queue q;

    q.enqueue(1);           
    q.enqueue(2);           
    q.enqueue(3);          
    cout << "Size of queue: " << q.getSize() << endl;      
    
    cout << "Front element: " << q.peek() << endl;         
    cout << "Removed element: " << q.dequeue() << endl;    
    
    cout << "Size of queue: " << q.getSize() << endl;      
    
    q.enqueue(4);         
    cout << "Front element: " << q.peek() << endl;        
    
    cout << "Is queue empty? " << (q.isEmpty() ? "Yes" : "No") << endl; 

    return 0;
}
