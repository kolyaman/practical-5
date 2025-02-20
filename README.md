Практична робота №5 Мануйленко Микола

    #include <stdio.h>

    #define MODULO 12345

    int main() {
    int input; 
    scanf("%d", &input);

    if (input == 1) {
        printf("2\n");
        return 0;
    }

    int state0 = 1, state1 = 1, state2 = 0;
    int temp0, temp1, temp2;

    for (int m = 2; m <= input; m++) {
        temp0 = (state0 + state1 + state2) % MODULO;
        temp1 = state0 % MODULO;
        temp2 = state1 % MODULO;

        state0 = temp0;
        state1 = temp1;
        state2 = temp2;
    }

    int final_result = (state0 + state1 + state2) % MODULO;
    printf("%d\n", final_result);

    return 0;
}
