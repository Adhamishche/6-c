1.Объявление массива строк.

char lines[3][30] = { "Privet.txt", "сочный", "арбуз"
};

2.Вывод имени файла

printf("Имя файла: %s\n", lines[0]);

3.Объединение строк в одну

char content[100]; int index = 0; for (int i = 1; i < 3; i++) { int j = 0; while (lines[i][j] != '\0') { content[index] = lines[i][j]; index++; j++; } content[index] = '\n'; index++; } content[index] = '\0';

4.Вывод содержимого файла

printf("\nСодержимое файла:\n%s", content);

Поиск слова в тексте

char target[] = "арбуз"; int contentLength = 0; int targetLength = 0;

while (content[contentLength] != '\0') { contentLength++; }

while (target[targetLength] != '\0') { targetLength++; }

5.Алгоритм поиска

int found = 0; for (int i = 0; i <= contentLength - targetLength; i++) { int match = 1; for (int j = 0; j < targetLength; j++) { if (content[i + j] != target[j]) { match = 0; break; } } if (match == 1) { found = 1; break; } }

6.Вывод результата поиска

if (found) { printf("\nСлово "%s" найдено в тексте\n", target); } else { printf("\nСлово "%s" не найдено\n", target); }
