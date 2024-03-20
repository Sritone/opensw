#성적 산출 프로그램
#2021041014_조현준

students_scores = []

for _ in range(5):
    name = input("학생의 이름?: ")
    English = int(input("그 학생의 영어 점수: "))
    Clanguage = int(input("그 학생의 C-언어 점수: "))
    Python = int(input("그 학생의 파이썬 점수: "))
    average = (English + Clanguage + Python) / 3
    students_scores.append([name, English, Clanguage, Python, average])

n = len(students_scores)
for i in range(n):
    max_idx = i
    for j in range(i+1, n):
        if students_scores[j][4] > students_scores[max_idx][4]:
            max_idx = j
    students_scores[i], students_scores[max_idx] = students_scores[max_idx], students_scores[i]

rank = 1
for i in range(n):

    average = students_scores[i][4]
    if average >= 90:
        grade = 'A'
    elif average >= 80:
        grade = 'B'
    elif average >= 70:
        grade = 'C'
    elif average >= 60:
        grade = 'D'
    else:
        grade = 'F'
    
    if i > 0 and students_scores[i][4] == students_scores[i-1][4]:
        same_rank = rank - 1
    else:
        same_rank = rank
    
    print(f"{students_scores[i][0]}- 평균 점수: {average:.2f}, 성적: {grade}, 등수: {same_rank}등.")
    rank += 1   
 
