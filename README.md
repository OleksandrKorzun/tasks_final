# tasks_final
taska = (input("change A,B or C"))


if taska == "A":
    list = input("Enter text for dictionary: ")
    edited_list = []
    output = ""
    for a in list.split():
        a = a.rstrip(",")
        a = a.rstrip(".")
        a = a.lower()
        if len(a) > 3:
            edited_list.append(a)
    edited_list = sorted(set(edited_list))

    for a in edited_list:
        output += a + "\n"
    print(output)


elif taska == "B":
    words = []
    a = input("Enter text for top 5 most reapeted words: ")
    words.extend(a.split())
    from collections import Counter
    counts = Counter(words)
    top5 = counts.most_common(5)
    print(top5)


elif taska == "C":
    def most_frequent(List):  
        cnt = 0
        word = ""
        for i in List:
            cur = List.count(i)
            if (cur > cnt) and (len(i) > 3):
                cnt = cur
                word = i

        for i in range(List.count(word)):
            mText.remove(word)
        return word, cnt


    mText = input("\n Введіть текст: ").split()

    mText = set(mText)
    mText = list(mText)
    mText.sort(reverse=True,
               key=len)

    for i in range(5):
        print(mText[i], len(mText[i]))
