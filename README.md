#include <iostream>

using namespace std;

void bubble(int *a,int n){
    bool did = false;
    int its =0;
    do{
        its++;
        did = false;
        for(int i=0;i<n-its;i++){
            if(a[i]>a[i+1]){
                int tmp = a[i];
                a[i]=a[i+1];
                a[i+1]=tmp;
                did = true;
            }
        }
    }while(did);
}

void osszeR(int a[] ,int b[],int n,int *c){
    int ap=0,bp=0,cp = 0;
    while (ap<n && bp<n){
        if(a[ap] >= b[bp]){
            c[cp]=b[bp];
            bp++;
            cp++;
        }else{
            c[cp] = a[ap];
            ap++;
            cp++;
        }

        if(ap == n){
            for(int i=bp;i<10;i++){
                c[cp] = b[i];
                cp++;
            }
        }else if(bp == n){
            for(int i=ap;i<10;i++){
                c[cp] = b[i];
                cp++;
            }
        }
    }
}
void ossze(int a[] ,int b[],int n,int *c){
    int ap=0,bp=0,cp = 0;
    bubble(a,n);
    bubble(b,n);
    while (ap<n && bp<n){
        if(a[ap] >= b[bp]){
            c[cp]=b[bp];
            bp++;
            cp++;
        }else{
            c[cp] = a[ap];
            ap++;
            cp++;
        }

        if(ap == n){
            for(int i=bp;i<n*2;i++){
                c[cp] = b[i];
                cp++;
            }
        }else if(bp == n){
            for(int i=ap;i<n*2;i++){
                c[cp] = b[i];
                cp++;
            }
        }
    }
}

int main()
{
    //int a[] = {1,4,9,13,20};
    int a[] = {57, 98, 81, 50, 92, 1, 87, 40, 99, 67, 27, 13, 53, 49, 85, 56, 32, 68, 65, 90, 36, 94, 12, 70, 77, 43, 16, 19, 3, 39, 47, 15, 88, 8, 55, 89, 24, 2, 58, 66, 51, 29, 62, 83, 63, 73, 22, 10, 34, 21, 14, 93, 86, 18, 84, 9, 7, 26, 100, 33, 71, 74, 91, 25, 4, 75, 45, 82, 95, 54, 11, 52, 42, 5, 37, 76, 38, 6, 60, 30, 17, 69, 23, 64, 79, 80, 31, 20, 46, 41, 61, 96, 28, 35, 72, 59, 44, 78, 97, 48};
    int b[] = {2, 13, 15, 35, 75, 36, 78, 8, 3, 21, 96, 10, 11, 61, 90, 43, 44, 88, 47, 62, 82, 33, 67, 66, 40, 46, 5, 70, 22, 26, 38, 49, 17, 77, 14, 12, 27, 31, 91, 6, 92, 16, 51, 55, 81, 39, 24, 48, 74, 9, 42, 86, 80, 64, 1, 69, 84, 65, 53, 100, 50, 83, 7, 60, 37, 58, 18, 34, 87, 72, 23, 94, 54, 63, 56, 68, 57, 59, 89, 95, 28, 52, 20, 99, 85, 97, 41, 71, 29, 4, 32, 19, 45, 25, 30, 93, 73, 76, 79, 98};
    int n = 100;
    int c[200];
    ossze(a,b,n,c);

    setlocale(LC_ALL,"hun");



    for(int i=0;i<10;i++){
        cout << "A tömb " << i+1 << ". eleme: " << c[i] << endl;
    }
}
