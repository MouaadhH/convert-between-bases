#include<stdio.h>
#include<math.h>
#include<string.h>


void inverse(char arr[]) {
    int size = strlen(arr);
    for (int i = 0; i <= size/2; i++) {
        char temp = arr[i];
        arr[i] = arr[size - 1 - i];
        arr[size - 1 - i] = temp;
    }
}

void coding(int N, int b) {
   
    // Work on the integer part ------------------------
    int T[32], i = 0; // Array and index
    int integerp = (int)N;   // Extract the integer part
     
    if (integerp == 0) {
        printf("0"); // Handle case where integer part is 0
    } else {
        while (integerp > 0) {
            T[i++] = integerp % b; // Store remainder
            integerp = integerp / b;// Update number
        }
        // Print remainders in reverse order
        for (i = i - 1; i >= 0; i--) { // Start from last stored index
         if(T[i]>9){
          printf(" %c", 'A'+ T[i]-10);
         }else{
            printf("%d", T[i]);
        }
    }
}}
void decoding(int N, int b){
    int integer_part = N ; // integer part
    int integer_result =0; // sum of integer
    int T[32]; // array to store separated digits

    if(integer_part == 0){
        printf("0");
    }
    else{
        int count = 0; //array index
        while (integer_part > 0) {
            T[count++] = integer_part % 10; // Get the last digit of the number
            integer_part = integer_part / 10;       // Remove the last digit by dividing the number by 10 
        }
            
        for (int i = count - 1 ; i >= 0 ; i--) {
            integer_result += T[i] * pow(b,i); // use the index of position as exponent 
        }     
    }
             printf("%d", integer_result); 
}
void transcodage_direct(char N[], int b) {
    int length = strlen(N);

    if (b == 4) {  
        // ----------- Base 4 Transcoding -----------
        
        char newN[length + 1]; // New string with extra space for padding
        if (length % 2 != 0) { // Add padding if length is odd
            newN[0] = '0'; // Add '0' at the start
            for (int i = 0; i < length; i++) {
                newN[i + 1] = N[i]; // Copy old bits
            }
            newN[length + 1] = '\0'; // Null-terminate the new string
            length++; // Update length
        } else {
            strcpy(newN, N); // Copy directly if length is even
        }

        int partsCount = length / 2; // Number of 2-bit groups
        char T[partsCount][3]; // Array to store 2-bit groups

        int index = 0;
        for (int i = 0; i < length; i += 2) {
            T[index][0] = newN[i];
            T[index][1] = newN[i + 1];
            T[index][2] = '\0'; // Null-terminate the group
            index++;
        }

        // Decode and print each 2-bit group
        for (int i = partsCount - 1; i >= 0; i--) {
            int first_bit = T[i][0] - '0';
            int second_bit = T[i][1] - '0';
            int decoded_value = first_bit * 2 + second_bit;
            printf("%d", decoded_value);
        }
    } else if (b == 8) { 
        // ----------- Base 8 Transcoding -----------

        char newN[length + 2]; // New string for padding
        if (length % 3 == 1) { // Add two '0's if remainder is 1
            newN[0] = '0';
            newN[1] = '0';
            for (int i = 0; i < length; i++) {
                newN[i + 2] = N[i];
            }
            newN[length + 2] = '\0'; // Null-terminate the new string
            length += 2; // Update length
        } else if (length % 3 == 2) { // Add one '0' if remainder is 2
            newN[0] = '0';
            for (int i = 0; i < length; i++) {
                newN[i + 1] = N[i];
            }
            newN[length + 1] = '\0';
            length++;
        } else {
            strcpy(newN, N); // Copy directly if divisible by 3
        }

        int partsCount = length / 3; // Number of 3-bit groups
        char T[partsCount][4]; // Array to store 3-bit groups

        int index = 0;
        for (int i = 0; i < length; i += 3) {
            T[index][0] = newN[i];
            T[index][1] = newN[i + 1];
            T[index][2] = newN[i + 2];
            T[index][3] = '\0'; // Null-terminate the group
            index++;
        }

        // Decode and print each 3-bit group
        for (int i = 0; i < partsCount; i++) {
            int first_bit = T[i][0] - '0';
            int second_bit = T[i][1] - '0';
            int third_bit = T[i][2] - '0';
            int base8_value = first_bit * 4 + second_bit * 2 + third_bit;
            printf("%d", base8_value);
        }
    } else if (b == 16) { 
        // ----------- Base 16 Transcoding -----------

        char newN[length + 3];
    }}
void transcoding(int N, int b , int y){
//######################################################################
//decoding
//######################################################################
   int T[32] , i;
   int e = (int)N ; // integer part
    int s=0; // sum of integer
     if(e == 0){
         printf("0");
     }
     else{
          int count = 0; 
          while (e > 0) {
              T[count] = e % 10; // Get the last digit of the number
              e = e / 10;       // Remove the last digit by dividing the number by 10
              count++;          // Increment the counter for the next digit
            }
             
          for (int i = count - 1 ; i >= 0 ; i--) {
                  s+=T[i]*pow(b,i); // use the index of position as exponent 
            }
        }
//###################################################################################
// coding
//###################################################################################  
   
          int t[32];
          i = 0; // Array and index
          e = s;   // Extract the integer part
       
       if (e == 0) {
           printf("0"); // Handle case where integer part is 0
        }else {
            while (e > 0) {
                 t[i++] = e % y; // Store remainder
                 e = e / y;      // Update number
            }
             // Print remainders in reverse order
           for (i = i - 1; i >= 0; i--) { // Start from last stored index
                 printf("%d", t[i]);
            }
        }
}
void DECIMAtoBCD(char number[], char result[]) {
    int size = strlen(number); // the number of digits in the decimal
    int bcd_bits_increase = 4; // keeps BCD bit limited (4bit)
    int index = 0; // used to track the current position in the result[]

    for (int i = size - 1; i >= 0; i--){
        int digit = number[i] - '0'; // turn digits into integers

        while (digit > 0) { // coding to binary
            int remainder = digit % 2;
            digit = digit / 2;
            result[index] = remainder + '0';// store redmainders as characters 
            index++;
        }

        while (index < bcd_bits_increase) { // adding zzeros to the digits starting ftom index to 4(2k)
            result[index] = '0';
            index++;
        }
        bcd_bits_increase += 4;
    }
    inverse(result);
    printf(" %s", result);
}
void bcdToDecimal(char bcd[]) {
    int decimal = 0;

    
    if (strlen(bcd) % 4 != 0) {// Check if the length of BCD input is valid
        printf("Invalid BCD input. Length should be a multiple of 4.\n");
        return;
    }

    for (int i = 0; i < strlen(bcd); i += 4) {// make groups of 4 digits
        int four_bit = 0;

        // Calculate the decimal value of 4 bit group
        for (int j = 0; j < 4; j++){
            four_bit = four_bit * 2 + (bcd[i + j] - '0');
        }

        // Check if the number is a valid decimal digit
        if (four_bit > 9) {
            printf("Invalid BCD input.\n");
            return;
        } 
                                   
        decimal = decimal * 10 + four_bit;// Build the decimal number
    }

    // Print the result
    printf(" %d\n", decimal);
}
void DECIMAtoBCDXtrois(char number[], char result[]) {
    int size = strlen(number);
    int bcd_bits_increase = 4;
    int index = 0;

    for (int i = size - 1; i >= 0; i--) {
        int digit = number[i] - '0' + 3;

        while (digit > 0) { // coding to binary
            int remainder = digit % 2;
            digit = digit / 2;
            result[index] = remainder + '0';
            index++;
        }

        while (index < bcd_bits_increase) { // adding zero
            result[index] = '0';
            index++;
        }
        bcd_bits_increase += 4;
    }
    inverse(result);
    printf("result is : %s", result);
}
void bcdpthreeToDecimal(char bcd[]) {
    int decimal = 0;

    
    if (strlen(bcd) % 4 != 0) {// Check if the length of BCD input is valid
        printf("Invalid BCD input. Length should be a multiple of 4.\n");
        return;
    }

    
    for (int i = 0; i < strlen(bcd); i += 4) {// make groups of 4 digits
        int four_bit = 0;

        // Calculate the decimal value of 4 bit group
        for (int j = 0; j < 4; j++){
            four_bit = (four_bit * 2 + (bcd[i + j] - '0'))-3;
        }

        // Check if the number is a valid decimal digit
        if (four_bit > 12 || four_bit < 3) {
            printf("Invalid BCD input. Nibbles must represent values between 3 and 12.\n");
            return;
        } 
                                   
        
        decimal = decimal * 10 + four_bit;// Build the decimal number
    }

    // Print the result
    printf("Decimal equivalent: %d\n", decimal);
}
void binary_to_gray(char binar[]) {
    printf("%c", binar[0]); // The first Gray code bit is the same as the first binary bit

    for (int i = 1; i < strlen(binar); i++) {
        // XOR current bit with the previous bit
        int digit = (binar[i - 1] - '0') ^ (binar[i] - '0');
        printf("%c", digit + '0'); // Print the Gray code bit
    }
}
void gray_to_binary(char gray[]) {
    printf("%c", gray[0]); // The first binary bit is the same as the first Gray code bit

    int prev_binary = gray[0] - '0'; // Keep track of the previous binary bit

    for (int i = 1; i < strlen(gray); i++) {
        // XOR the previous binary bit with the current Gray code bit
        int current_binary = prev_binary ^ (gray[i] - '0');
        printf("%c", current_binary + '0');
        prev_binary = current_binary; // Update the previous binary bit
    }
}
void binary_addition(int N1, int N2) {
    int temp1 = N1, temp2 = N2;

    // Validate if the first number is binary
    while (temp1 > 0) {
        if (temp1 % 10 > 1) {
            printf("Error: First number is not binary\n");
            return;
        }
        temp1 /= 10;
    }

    // Validate if the second number is binary
    while (temp2 > 0) {
        if (temp2 % 10 > 1) {
            printf("Error: Second number is not binary\n");
            return;
        }
        temp2 /= 10;
    }

    int result = 0;
    int carry = 0;
    int multiplier = 1;

    // Perform binary addition
    while (N1 > 0 || N2 > 0 || carry > 0) {
        int bit1 = N1 % 10; // Extract last digit of N1
        int bit2 = N2 % 10; // Extract last digit of N2

        int sum = bit1 + bit2 + carry;
        carry = sum / 2; // Calculate carry
        result += (sum % 2) * multiplier; // Append the current bit to the result

        // Move to the next digit
        N1 /= 10;
        N2 /= 10;
        multiplier *= 10;
    }

    printf("Result: %d\n", result);
}

int main() {
    int base_from, base_to, num, num1, num2;
    char str[512], result[512];
    char response_type[16], response_conversion[16];
    char response_reload ;
do{   
    printf("Would you like to do:\n1 - Conversions\n2 - Binary Addition\nChoose: ");
    scanf("%d", &num1);

    if (num1 == 1) {
        printf("\nWhat is your current position (write 'base' or 'type' for BCD, Gray, BCD+3): ");
        scanf("%s", response_type);

        if (strcmp(response_type, "base") == 0) {
            printf("Enter your current base: ");
            scanf("%d", &base_from);
            printf("Enter the number: ");
            scanf("%d", &num);
            printf("What would you convert to ('base' or 'type')? ");
            scanf("%s", response_conversion);

            if (strcmp(response_conversion, "base") == 0) {
                printf("Enter the target base: ");
                scanf("%d", &base_to);
                
                if (base_from == 10) {
                    printf("\n%d in base %d is: ", num, base_to);
                    coding(num, base_to);
                } else if (base_to == 10) {
                    printf("\n%d in decimal is: ", num);
                    decoding(num, base_from);
                } else {
                    printf("\n%d in base %d is: ", num, base_to);
                    transcoding(num, base_from, base_to);
                }
            } else if (strcmp(response_conversion, "type") == 0) {
                printf("\nConvert to BCD, Gray, or BCD+3: ");
                scanf("%s", response_conversion);

                if (strcmp(response_conversion, "BCD") == 0) {
                    if (base_from == 10) {
                        sprintf(str, "%d", num);
                        DECIMAtoBCD(str, result);
                        printf("\n%d in BCD is: %s", num, result);
                    } else {
                        printf("**Please enter a decimal number.\n");
                    }
                } else if (strcmp(response_conversion, "BCD+3") == 0) {
                    if (base_from == 10) {
                        sprintf(str, "%d", num);
                        DECIMAtoBCDXtrois(str, result);
                        printf("\n%d in BCD+3 is: %s", num, result);
                    } else {
                        printf("**Please enter a decimal number.\n");
                    }
                } else if (strcmp(response_conversion, "Gray") == 0) {
                    if (base_from == 2) {
                        sprintf(str, "%d", num);
                        binary_to_gray(str);
                    } else {
                        printf("**Please enter a binary number.\n");
                    }
                } else {
                    printf("Invalid conversion type.\n");
                }
            } else {
                printf("Invalid response.\n");
            }
        } else if (strcmp(response_type, "type") == 0) {
            printf("Enter the current type (BCD, BCD+3, Gray): ");
            scanf("%s", response_conversion);

            printf("Enter the number: ");
            scanf("%s", str);

            if (strcmp(response_conversion, "BCD") == 0) {
                printf("Representation in Decimal is: ");
                bcdToDecimal(str);
            } else if (strcmp(response_conversion, "BCD+3") == 0) {
                printf("Representation in Decimal is: ");
                bcdpthreeToDecimal(str);
            } else if (strcmp(response_conversion, "Gray") == 0) {
                printf("Representation in Binary is: ");
                binary_to_gray(str);
            } else {
                printf("Invalid type.\n");
            }
        } else {
            printf("Invalid response.\n");
        }
    } else if (num1 == 2) {
        printf("Enter the first binary number: ");
        scanf("%d", &num);
        printf("Enter the second binary number: ");
        scanf("%d", &num2);
        binary_addition(num, num2);
    } else {
        printf("Invalid choice.\n");
    }
    
    printf("\ndo you want to start another process (Y/N) ? :"); scanf(" %c", &response_reload);
}while(response_reload != 'N');
    return 0;
}
