def input_student_info():
    students = []  
    for _ in range(5):  
        student_id = input("학번: ")
        name = input("이름: ")
        english = int(input("영어: "))
        c_language = int(input("C-언어: "))
        python = int(input("파이썬: "))
        
       
        student_info = {
            "학번": student_id,
            "이름": name,
            "영어": english,
            "C-언어": c_language,
            "파이썬": python
        }
        
        # 학생 정보 리스트에 추가
        students.append(student_info)
    return students

def calculate_total_and_average(student):
    total = student["영어"] + student["C-언어"] + student["파이썬"]
    average = total / 3
    return total, average

def assign_grade(average):
    if average >= 90:
        return "A"
    elif average >= 80:
        return "B+"
    elif average >= 70:
        return "B"
    elif average >= 60:
        return "C+"
    else:
        return "F"

def calculate_rank(students):
    # 총점을 기준으로 학생들을 내림차순 정렬
    sorted_students = sorted(students, key=lambda x: x["총점"], reverse=True)
    for i, student in enumerate(sorted_students):
        student["등수"] = i + 1

def print_students_info(students):
    print("\t\t\t\t\t성적관리 프로그램\n")
    print("=" * 89)
    print(f"{'학번':<15}{'이름':<10}{'영어':<10}{'C-언어':<10}{'파이썬':<10}{'총점':<10}{'평균':<10}{'학점':<10}{'등수':<5}")
    print("=" * 89)
    for student in students:
        print(f"{student['학번']:<15}{student['이름']:<10}{student['영어']:<10}{student['C-언어']:<10}{student['파이썬']:<10}{student['총점']:<10}{student['평균']:<10.2f}{student['학점']:<10}{student['등수']:<5}")
    print("=" * 89)

def main():
    students = input_student_info()
    for student in students:
        total, average = calculate_total_and_average(student)
        student["총점"] = total
        student["평균"] = average
        student["학점"] = assign_grade(average)
    calculate_rank(students)
    print_students_info(students)

if __name__ == "__main__":
    main()
