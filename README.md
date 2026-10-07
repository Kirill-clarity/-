#include <iostream>
#include <vector>
#include <cstdlib>
#include <ctime>

int main() {
    srand(time(0));

    int n1 = 4; 
    int n2 = 6;

    std::vector<int> a(n1);
    std::vector<int> b(n2);

    std::cout << "Число 1: ";
    for (int i = 0; i < n1; i++) {
        a[i] = rand() % 9 + 1; 
        std::cout << a[i];
    }
    std::cout << "\n";

    std::cout << "Число 2: ";
    for (int i = 0; i < n2; i++) {
        b[i] = rand() % 9 + 1;
        std::cout << b[i];
    }
    std::cout << "\n";

    std::vector<int> res;
    int i = n1 - 1; 
    int j = n2 - 1; 
    int carry = 0;  

    while (i >= 0 || j >= 0 || carry > 0) {
        int sum = carry;

        if (i >= 0) sum += a[i--]; 
        if (j >= 0) sum += b[j--]; 

        res.push_back(sum % 10);   
        carry = sum / 10;         

    std::cout << "Сума:    ";
    for (int k = res.size() - 1; k >= 0; k--) {
        std::cout << res[k];
    }
    std::cout << "\n";

    return 0;
}
