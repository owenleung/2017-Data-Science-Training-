# 2017-Data-Science-Training-
# Part 1 List Exercise 

def match_ends(words):
    count = 0
    for i in words:
        if len(i) >= 2 and i[0] == i[len(i)-1]:
            count += 1
    return count
    
def front_x(words):
    words.sort ()
    for i in words:
        if i[0] == "x":
            words.remove (i)
            words.insert (0, i)
    return words
    
def sort_last(a_list):
    sorted_list = sorted(a_list,key=last)
    return sorted_list
 
def remove_adjacent(nums):
    i = 0
    while i < len(nums)-1:
        if nums[i] == nums[i+1]:
            del nums[i]
            i += 1
        else:
            i += 1
    return nums
  
def merge(first, second):
    final = []
    i = len(first)
    j = len(second)
    total = i + j
    x = y = 0
    while len(final) != total:
        if x == i:
            final += second[j:]
            break
        elif y == j:
            final += first[x:]
            break
        elif first[x] > second[y]:
            final.append (second[y])
            y += 1
        elif first[x] < second[y]:
            final.append (first[x])
            x += 1
    return final

# Part 1 String Exercise 

def donuts(count):
    standard = "Number of donuts: "
    if count >= 10:
        standard += "many"
    else:
        standard += str(count)
    return standard
   
def both_ends(s):
    if len(s) < 2:
        s = ""
    else:
        s = s[0:2] + s[-2] + s[-1]
    return s
 
def fix_start(s):
    save_the_first = s[0]
    transform = s.replace(s[0],"*")
    final = save_the_first + transform[1:] 
    return final
   
def mix_up(a, b):
    a_first_2_char = a[0:2] 
    b_first_2_char = b[0:2]
    swap1 = a_first_2_char + b[2:] 
    swap2 = b_first_2_char + a[2:] 
    final = swap2 + " " + swap1
    return final
 
def verbing(s):
    if len(s) > 3 and s[-3:] == "ing":
        s += "ly"
    elif len(s) > 3 and s[-3:] != "ing":
        s += "ing"
    return s
 
def not_bad(s):
    if s.find("not") and s.find("bad") != -1:
        location_not = s.find("not")
        location_bad = s.find("bad") + 3
        s = s.replace(s[location_not:location_bad], "good")
    return s
 
def front_back(a, b):
    if len(a)%2 != 0:
        a_front = a[0:int(len(a)//2) + 1]
        a_back = a[int(len(a)//2):]
    else:
        a_front = a[0:int(len(a)/2)]
        a_back = a[int(len(a)/2):]
    if len(b)%2 != 0:
        b_front = b[0:int(len(b)//2) + 1]
        b_back = b[int(len(b)//2):]
    else:
        b_front = b[0:int(len(b)/2)]
        b_back = b[int(len(b)/2):]

    return a_front + b_front + a_back + b_back
