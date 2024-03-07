#include <stdio.h>
#include <stdlib.h>

int main() {
    int n;
    scanf("%d", &n);

    // Khởi tạo mảng đếm số lần xuất hiện
    int* count = (int*)calloc(1000000000, sizeof(int));

    // Đọc dãy số và đếm số lần xuất hiện
    for (int i = 0; i < n; ++i) {
        int value;
        scanf("%d", &value);
        ++count[value + 500000000];
    }

    // In kết quả
    int uniqueCount = 0;
    for (int i = 0; i < 1000000000; ++i) {
        if (count[i] > 0) {
            printf("%d %d\n", i - 500000000, count[i]);
            ++uniqueCount;
        }
    }
    printf("%d\n", uniqueCount);

    // Giải phóng bộ nhớ
    free(count);

    return 0;
}
