java c
PROGRAMMING 
COMPSCI 4039 
Thursday 30 April 2020
1. For   each   of   the   following   code   snippets,   write   the   output   that   the   code   would   produce   and   describe   why   the   output   is   as   it   is,   paying particular   attention   to   the   looping criteria: how i is initialized, how and when it is changed, and how the loop terminates.  
(a) 
for(int i=0;i<5;i++) { 
System.out.println(i); 
} [1 mark] 
(b) 
for(int i=1;i<7;i*=2) { 
System.out.println(i); 
} [1 mark] 
(c) 
int i = 0; 
while(i<3) { 
System.out.println(i++); 
} [1 mark] 
(d) 
int i = 3; 
while(i<5) { 
System.out.println(++i); 
} [1 mark] 
(e) 
int i = 5; 
do { 
System.out.println(i); 
i+=1; 
}while(i<4); [1 mark]
2.                                              Examine the following class and answer the questions below:
1.                      public class Mystery { 
2.                                                       public static int c = 0; 
3.                                                       public static void main(String[] args) { 
4.                                                                                        int[] a = {8,1,-3,12,4}; 
5. System.out.println(go(a,0,a.length)); 
6. } 7. 
8.                                                       public static int go(int[] a,int le,int ri) { 
9. c += 1; 
10.                                                                                     if(ri - le <= 1) { 
11.  return a[le]; 
12. } 
13.  else { 
14.                                                                                                                   int cp = le+(ri-le)/2; 
15.  int m1 = go(a,le,cp); 
16.  int m2 = go(a,cp,ri); 
17.  if(m1 > m2){ 
18. return m1; 
19.  }else { 
20.  return m2; 
21. } 
22. } 
23. } 
24. } 
(a)             The main   method   passes   an   array   of   type   int   to   the   method   go.   From   examining   the   code, deduce   what   useful   property   ofthe   array   the   method   go   returns.                            [1 mark]
(b)             This program makes use of   a particular programming style. described   in   the   course (see e.g. line   15).   What   is   it?           [1 mark]
(c)             Describe how the   program achieves its goal. In   particular, step through the different   calls   to   the   go   method,   in   the   order   in   which   they   happen,   and   what   the   method returns. You do not need togo through all the calls (there will be 9 in this example),   just   enough   to   be   able   to   describe   how   the   program   works. [6 marks]
(d)             If the   input   array   was   changed   to    {1,4,10,3,10}   which   position   in   the   array   would the value returned by the first call to go   (line   5)   correspond   to?   Justify your   answer. The first position is position zero.       [3 marks]
(e)             The   program   currently   only   works   with    int   arrays.   Describe   any   modifications   you would make to the original code that would allow it   to   work   with   any   type   for   which is possible to compare two elements.            [4 marks]
3. Study the following class and then answer the   questions below.
1.                      public class ExamQ3 { 
2. private int a; 
3.                                                       public ExamQ2(int b) { 
4. a = b; 
5. } 
6.                                                       private int getA() { 
7. return a; 
8. } 
9.                                                       private void setA(int b) { 
10.  a = b; 
11. } 
12.                                                 public String toString() { 
13. return "" + a; 
14. } 
15.                                                 public static void add3(int a) { 
16. a += 3; 
17. } 
18.  public static void add3Obj(ExamQ2 e) { 
19. e.setA(3 + e.getA()); 
20. } 
21.                                                 public static void main(String[] args) { 
22.  int a = 5; 
23.  ExamQ2 ee = new ExamQ2(a); 
24. add3(a); 
25.  System.out.println(a); 
26. add3Obj(ee); 
27. System.out.println(ee.getA()); 
28. } 
29. } 
(a) What   is   the   meaning   of private online   2?                   [1 mark]
(b) Line    9      contains      a    method      signature.      Copy      the      signature,      and      label      each      of    its   components, describing their   meaning.    [2 marks]
(c) Overriding, overloading, interfaces, superclasses and subclasses   are   all   concepts   and   phenomena that we use when building object oriented programs. One is used in this    example.   State which one,   and on which line.        [1 mark]
(d) Describe all of   the things being   created   on   line 23.           [2 marks]
(e) The four lines starting from line 24 contain two calls to methods that add 3 to an integer.   State the outputs at lines 25   and 27.   Describe   in   detail   why   you   believe   the   outputs   are   as you have   stated.                    [4 marks]
4. A   local   school   awards   pupils   with   points   for   performing   good   deed代 写COMPSCI 4039 PROGRAMMING 2020Java
代做程序编程语言s   in   the   class   (tidying up, helping others, etc). At the end of   each week, the pupil with the highest   number   of   points   wins   a   prize.   You   are   part   of   a   team   that   has   been   asked   by   the school to help them write a program to keep track of   the points each week and why   they were   awarded.   The   program   stores   the   current points   in   a   text   file,   in   which   each   line   corresponds   to   one   instance   of a pupil   having been   awarded points   (i.e.   each pupil may appear in multiple lines):(and the fields are separated by spaces). When the program is run, it first loads this   file,   storing   the   data,   and   then waits   for the user   to   type   an   input.   There   are   three   types   of   input:
The user can add points to a   student by typing:
ADD      
(again, fields separated by spaces). You can assume that    will   never   include any spaces, both here and in the   original   file.
The user can reset all pupils to having no points with:   RESET
Or   list   all   pupils   in   descending   order   of   total   points   with:   LIST
(a) The   team   decides   to   solve   this   problem   with   a   solution   that   includes   a   class   Pupil,   objects   of   which   will   represent   each   pupil    and   a   class   AwardedPoints that   will   represent   a particular   instance   of   points being   awarded   to   a   student.   The   Pupil   class   should store references to all instances of   points awarded to that pupil. Provide code for   a suitable AwardedPoints   class. Justify all attributes and methods   you   include   based   on   the   problem   description   above.   It   should   be   possible   to   make   an   object   with   or   without   a   String   argument representing   . You do not   need   to   include   import   statements   in   any   code   in   this   question.   Use   only   Java   classes   we   covered in the   course.    [3 marks]
(b) Provide code for a suitable   Pupil   class.   Justify   any methods   you   include   based   on   the   problem   description   above.   You   can   assume   that   any particular   Pupil   will   never   be   awarded points more than   100 times.    [6 marks]
(c) Two   Pupil   objects will be defined as equal if   they share the   same   first   and   second
names. Write a    .equals(Object o)   method for your class that meets this specification. You can assume throughout that two different pupils never share both   a   first and   second name. [3 marks]
(d) It   is   decided   to   implement   the   ADD   command   by   creating   a   new   temporary Pupil   object   with   the   data   entered   by the   user   in   the   ADD   command.   This   temporary   Pupil   object   will   then   be   compared   against   all   pupils   in   the   array to   find   a   match   using   the   .equals   method (from part (d)). Write a method that takes as its arguments the Pupil   array, a reference to an individual Pupil   object and to an AwardedPoints   object. The   method should find the entry in the array that matches the individual   Pupil   object and   add   the   AwardedPoints   object   to   the   pupil. If   the   pupil   does   not   exist   in   the   array,   it should be added to the array.       [4 marks]
(e) Write code to read the data file and   store the results into an array of   Pupil   objects. You   do   not   need   to   include   exception   handling   and   you   can   assume   that   the   data   file   is   always   correctly formatted.   The   first   line   of   the   file   corresponds   to   the   first pupil   (i.e.   there   are   no   headers   in   the   file).   You   can   assume   there   will   never   be   more   than   100   pupils.       [4 marks]
(f) Assume that another team member has provided a compareTo   method allowing you to   use Arrays.sort   to   sort your   Pupil   array   so that the highest   scoring pupil   is   in   the   first   position.   Write   code   that   will   prompt   the   user   for   input,   parse   the   input,   decide   upon   the   relevant   action   and   then   perform   that   action.   You   can   assume   that   the   user   always enters the data   correctly.       [4 marks]
(g) Other team members are programmers but are   not experienced in   object   oriented   (OO)   programming.   Describe   to   them   four benefits   of   an   OO   approach   for this   application.   Be as specific as possible, ensuring that you make reference to features of   this particular   program. As they are   programmers, you can assume that they are familiar with concepts   like   variables   and   methods.   Each   benefit   should   require   no   more   than   one   or   two   sentences.       [4 marks]
(h) Within   the   team,   before   development   you   discussed   two   possible   solutions.   One   that   consisted   of   just   a   Pupil   class   and   the   one   that   was   ultimately   chosen   consisting   of   separate classes to represent   Pupils   and AwardedPoints. Describe   why   the   second   option is better. Ensure your answer is specific to this application, and not an argument   for object orientation in   general.       [2 marks]

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
