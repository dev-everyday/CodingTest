# 문제

회사 식당에는 전설처럼 전해 내려오는 비밀 메뉴에 대한 소문이 있다. 소문의 내용은 대강 이러하다.

식권 자판기의 버튼을 특정 순서대로 누르고 결제를 하면, 평소와는 다른 색깔의 식권이 나온다.

이 식권을 배식대에 제출하면, 어떤 비밀 메뉴를 받을 수 있다는 것이다. 물론 이를 실제로 본 사람은 아무도 없어서, 어떤 메뉴가 나오는지는 커녕 눌러야 하는 버튼의 순서조차 알려져 있지 않다.

주방장인 당신은 이 소문의 실체를 알고 있다. 이는 분명한 사실이다!

정해진 버튼 조작법을 사용하면 비밀 메뉴의 식권을 얻을 수 있다. 그러나 얼마 전 식권 자판기가 고장으로 교체되면서, 새 자판기에서는 비밀 메뉴 조작법이 작동하지 않게 되었다.

당신은 프로그래밍 실력을 살려, 사용자의 버튼 조작 중 비밀 메뉴 조작법이 포함되어 있는지를 판단하는 회로를 추가하려 한다.

자판기에는 총 K개의 버튼이 있다. 각 버튼마다 1부터 K까지 번호가 붙어 있어서, 조작 과정은 1 이상 K 이하의 정수 여러 개로 나타낼 수 있다.

비밀 메뉴 조작법은 M개의 버튼 조작으로 이루어져 있으며, 이 순서대로 버튼을 누르면 반드시 비밀 메뉴 식권이 발매된다. 이때, 이 조작법 앞뒤로 다른 버튼 조작이 있어도 비밀 메뉴로 인정된다.

사용자가 누른 N개의 버튼 조작이 주어질 때, 사용자가 비밀 메뉴 식권을 받을 수 있는지를 확인하는 프로그램을 작성하여라.

# 풀이

간단하게 a와 b 문자열을 만들어준 후 b가 a를 포함하는지(포함하지 않으면 string::npos) 판단해서 출력하면 된다.

# 코드
```
#include<iostream>
#include<string>
using namespace std;
int n, m, k;
int secret[101];
int oper[101];

int main(int argc, char** argv)
{
    scanf("%d %d %d",&m, &n, &k);
    string a, b;
    for(int i=0;i<m;i++){
        scanf("%d",&secret[i]);
        a += to_string(secret[i]); 
    }
    for(int i=0;i<n;i++){
        scanf("%d",&oper[i]);
        b += to_string(oper[i]);

    }
    if (b.find(a) != string::npos) { 
        cout << "secret" << endl;
    } else {
        cout << "normal" << endl;
    }
    return 0;
}
```
```
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        int m = sc.nextInt();
        int n = sc.nextInt();
        int k = sc.nextInt();
        
        StringBuilder a = new StringBuilder();
        StringBuilder b = new StringBuilder();

        for (int i = 0; i < m; i++) {
            int num = sc.nextInt();
            a.append(num);
        }

        for (int i = 0; i < n; i++) {
            int num = sc.nextInt();
            b.append(num); 
        }

        if (b.toString().contains(a.toString())) {
            System.out.println("secret");
        } else {
            System.out.println("normal");
        }

        sc.close();
    }
}
```