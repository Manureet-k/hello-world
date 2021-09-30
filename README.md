import mysql.connector
from time import*

def merge_sort(self, sequence):
    if len(sequence) < 2:
        return sequence
    mid = len(sequence)/2
    leftsequence = self.merge_sort(sequence[:mid])
    rightsequence = self.merge_sort(sequence[mid:])

    return merge(leftsequence, rightsequence)

def merge(left, right):
    result = []
    i = j = 0
    while i < length(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i = i + 1
        else:
            result.append(right[j])
            j = j + 1
    result = result + left[i:]
    result = result + right[j:]

    return result


print("Name: Manureet Kaur\nRoll No. 1905020")
con = mysql.connector.connect(user="root",
                    password=" ",
                    host="localhost",
                    database="daa")
cursor = con.cursor()
cursor.execute("select * from student1")
rows = cursor.fetchall()
list = []
for row in rows:
    roll_no = row[0]
    list.append(roll_no)

print("\nList before sorting\n", list)
print()
timestamp1 = time()
print("List after sorting: \n", merge_sort(list))
timestamp2 = time()
print("Time taken for merge sort: ", timestamp2-timestamp1)
