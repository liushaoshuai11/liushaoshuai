#!usr/bin/python
#diercizuoye.pydef
length=int(raw_input('Enter an integer:'))
#lencounter=length
import random
from fractions import Fraction
a=['+', '-', '*', '/']
m=0
score=0
ans=0
def  yuns2(x,y,o):
    if o=='+':
        return x+y
    if o=='-':
        return x-y
    if o=='*':
        return x*y
    if o=='/':
        return Fraction(x,y)
def opis(o1,o2,o3):
    op=0
    if o1=='+' :
        op=op+100
    elif o1=='-':
        op=op+100
    else:
        op=op+200
    if o2=='+' :
        op=op+10
    elif o2=='-':
        op=op+10
    else:
        op=op+20
    if o3=='+' :
        op=op+1
    elif o3=='-':
        op=op+1
    else:
        op=op+2
    return op
def opis2(o11,o12,o13):
    op1=0
    if o11=='+'and o12=='+':
        op1=op1+12
    elif o11=='-'and o12=='-':
        op1=op1+12
    elif o11=='*'and o12=='*':
        op1=op1+12
    elif o11=='/'and o12=='/':
        op1=op1+12
    elif o11=='+'and o13=='+':
        op1=op1+13
    elif o11=='-'and o13=='-':
        op1=op1+13
    elif o11=='*'and o13=='*':
        op1=op1+13
    elif o11=='/'and o13=='/':
        op1=op1+13
    elif o12=='+'and o13=='+':
        op1=op1+23
    elif o12=='-'and o13=='-':
        op1=op1+23
    elif o12=='*'and o13=='*':
        op1=op1+23
    elif o12=='/'and o13=='/':
        op1=op1+23
    else:
        op1= opis(o11,o12,o13)
        return op1
for i in range(1, length + 1):
    number1=random.randint(1,100)
    number2=random.randint(1,100)
    number3=random.randint(1,100)
    number4=random.randint(1,100)
    number5=random.randint(1,100)
    number6=random.randint(1,100)
    n1 = random.choice(a)
    n2 = random.choice(a)
    n3 = random.choice(a)
    if number3<number4:
        f1=Fraction(number3,number4)
    else:
        f1=Fraction(number4,number3)
    if number5 < number6:
        f2=Fraction(number5,number6)
    else:
        f2=Fraction(number6,number5)
    print number1, n1, number2, n2, f1, n3, f2, '='
    if opis2(n1,n2,n3)==12:
        ans=yuns2(yuns2(number1,number2,n1),f1,n2)
        print ans
        res = Fraction(raw_input('The result is:'))
        if res == ans:
            print 'Right!'
            m=m+1
            score=score+1
        else:
            print 'Wrong!'
            print 'The right answer is',ans
    elif opis2(n1,n2,n3)==13:
        ans=yuns2(yuns2(number1,number2,n1),f2,n3)
        print ans
        res = Fraction(raw_input('The result is:'))
        if res == ans:
            print 'Right!'
            m=m+1
            score=score+1
        else:
            print 'Wrong!'
            print 'The right answer is',ans
    elif opis2(n1,n2,n3)==23:
        ans=yuns2(yuns2(number2,f1,n2),f2,n3)
        print ans
        res = Fraction(raw_input('The result is:'))
        if res == ans:
            print 'Right!'
            m=m+1
            score=score+1
        else:
            print 'Wrong!'
            print 'The right answer is',ans
    elif opis(n1,n2,n3)==111:
        ans=yuns2(yuns2(yuns2(number1,number2,n1),f1,n2),f2,n3)
        print ans
        res = Fraction(raw_input('The result is:'))
        if res == ans:
            print 'Right!'
            m=m+1
            score=score+2
        else:
            print 'Wrong!'
            print 'The right answer is',ans
    elif opis(n1, n2, n3) == 112:
        ans = yuns2(yuns2(yuns2(f1, f2, n3), number1, n1), number2, n2)
        print ans
        res = Fraction(raw_input('The result is:'))
        if res == ans:
            print 'Right!'
            m = m + 1
            score = score + 3
        else:
            print 'Wrong! '
            print 'The right answer is', ans
    elif opis(n1, n2, n3) == 121:
         ans = yuns2(yuns2(yuns2(number2, f1, n2), number1, n1), f2, n3)
         print ans
         res = Fraction(raw_input('The result is:'))
         if res == ans:
             print 'Right!'
             m = m + 1
             score = score + 3
         else:
              print 'Wrong! '
              print 'The right answer is', ans
    elif opis(n1, n2, n3) == 122:
          ans = yuns2(yuns2(yuns2(number2, f1, n2), f2, n3), number1, n1)
          print ans
          res = Fraction(raw_input('The result is:'))
          if res == ans:
              print 'Right!'
              m = m + 1
              score = score + 3
          else:
              print 'Wrong! '
              print 'The right answer is', ans
    elif opis(n1, n2, n3) == 211:
          ans = yuns2(yuns2(yuns2(number1, number2, n1), f1, n2), f2, n3)
          print ans
          res = Fraction(raw_input('The result is:'))
          if res == ans:
              print 'Right!'
              m = m + 1
              score = score + 3
          else:
              print 'Wrong! '
              print 'The right answer is', ans
    elif opis(n1, n2, n3) == 212:
          ans = yuns2(yuns2(number1, number2, n1),yuns2(f1, f2, n3) , n2)
          print ans
          res = Fraction(raw_input('The result is:'))
          if res == ans:
              print 'Right!'
              m = m + 1
              score = score + 3
          else:
              print 'Wrong! '
              print 'The right answer is', ans
    elif opis(n1, n2, n3) == 221:
          ans = yuns2(yuns2(yuns2(number1,number2,n1),f1,n2),f2,n3)
          print ans
          res = Fraction(raw_input('The result is:'))
          if res == ans:
              print 'Right!'
              m = m + 1
              score = score + 3
          else:
              print 'Wrong! '
              print 'The right answer is', ans
    elif opis(n1, n2, n3) == 222:
          ans = yuns2(yuns2(yuns2(number1, number2, n1), f1, n2), f2, n3)
          print ans
          res = Fraction(raw_input('The result is:'))
          if res == ans:
              print 'Right!'
              m = m + 1
              score = score + 2
          else:
              print 'Wrong! '
              print 'The right answer is', ans
m=float(m)
length=float(length)
print 'The test is over.'
print 'The number of right answers is',m
print 'Your score is',score
print 'The correct rate is',m/length*100,'%'
