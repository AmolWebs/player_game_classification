'''

In second year computer engineering class, group A student’s play cricket, group B
students play badminton and group C students play football. Write a
Python program using functionsto compute following: -
a) List ofstudents who play both cricket and badminton
b) List ofstudents who play either cricket or badminton but not both
c) Number ofstudents who play neither cricket nor badminton
d) Number ofstudents who play cricket and football but not badminton.
(Note- While realizing the group, duplicate entries should be avoided, Do not use
SET built-in functions)

'''
# list for gettting name of all participants

def All_participants(num,all_list):
    i = 1
    while i<=num:
        a = input("Enter name : ")
        if a in all_list:
            pass
        else:
            all_list.append(a)
        i+=1
    return all_list

# list for getting name of group A stdents who plays cricket

def cricket_participants(crick_part,crick_list):
    i = 1
    while i<=crick_part:
        a = input("Enter your name : ")
        crick_list.append(a)
        i+=1
    return crick_list
        
# list for getting name of group B students who plays badminton

def badminton_participants(badm_part,badm_list):
    i = 1
    while i<=badm_part:
        a = input("Enter your name : ")
        badm_list.append(a)
        i+=1
    return badm_list


# list for getting name of students who plays football 

def football_participants(footb_part,footb_list):
    i = 1
    while i<=footb_part:
        a = input("Enter your name : ")
        footb_list.append(a)
        i+=1
    return footb_list
# list for getting name of students who only plays cricket or badminton

def only_crick_badm(crick_list,badm_list,crick_badm,only_crick_or_badm):
    new_list =[]
    new_list = crick_list + badm_list
    only_crick_badm =[item for item in new_list if item not in crick_badm]
    return only_crick_badm

# list for getting name of students who plays both cricket and badminton
def dup_cric_badm(crick_list,badm_list,crick_badm):
    for i in crick_list:
        for j in badm_list:
            if(i==j):
                crick_badm.append(j)
    return crick_badm
    
# list for getting name of students who neither plays cricket or badminton

def neither_crick_badm(all_participants,crick_list,badm_list,neither_crick_badm):
    new_list = []
    new_list = crick_list + badm_list
    neither_crick_badm = [item for item in all_participants if item not in new_list]
    return neither_crick_badm


# list for getting name of students who plays both cricket and football

def both_crick_footb(crick_list,footb_list,crick_footb):
    for i in crick_list:
        for j in footb_list:
            if(i==j):
                crick_footb.append(j)
    return crick_footb
    
# list for getting name of students who plays both cricket and football but not badminton
def crick_foot_notBadm(crick_footb,badm_list,crick_foot_nbad):
    crick_foot_nbad = []
    
    for i in crick_footb:
        for j in badm_list:
            if (i != j):
                if (i in crick_foot_nbad):
                    pass
                else:
                    crick_foot_nbad.append(i)
    return crick_foot_nbad
    
    

while True:
    print("-----------------------------------------------------------------------------------------------------")
    participants = input("\n\nEnter no. of students who plays any one of the game : ")
    if participants == "Exit":
        break
    else:
        participants = int(participants)
    
    all_participants = []
    neither_crick_badm_part = []
    crick_list = []
    badm_list = []
    footb_list = []
    crick_badm = []
    crick_footb = []
    only_crick_or_badm =[]
    crick_foot_nbad =[]
    print(All_participants(participants,all_participants))
    participants = len(all_participants)
    crick_part = int(input("Enter no. of students who plays cricket : "))
    print(cricket_participants(crick_part,crick_list))
    badm_part = int(input("Enter no. of students who plays badminton : "))
    print(badminton_participants(badm_part,badm_list))
    footb_part = int(input("Enter no. of students who plays football : "))
    print(football_participants(footb_part,footb_list))
    print("Student who plays both cicket and badminton : ",dup_cric_badm(crick_list,badm_list,crick_badm))
    print("Students who plays either cricket or badminton not both : ",only_crick_badm(crick_list,badm_list,crick_badm,only_crick_or_badm))
    print("Students who neither plays cricket or badminton : ",neither_crick_badm(all_participants,crick_list,badm_list,neither_crick_badm_part))
    print("Student who plays cricket and football : ",both_crick_footb(crick_list,footb_list,crick_footb))
    print("Student who plays cricket and football but not badminton : ",crick_foot_notBadm(crick_footb,badm_list,crick_foot_nbad) )
