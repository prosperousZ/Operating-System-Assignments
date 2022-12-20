#include "assignment1.h"
#include <fcntl.h>
//int main()
//{
  
  //uint64_t num  = 0x0403deadbeef0201;
 // num = byte_sort(num);
 // printf("0x%016lx\n", num);
 // uint64_t num1 = 0x0403deadbeef0201;
   
 //num1 = nibble_sort(num1);
//printf("0x%016lx\n",num1);
//const char* output = "Haoze";
 //printf("%c\n", str_to_list(output)-> link->link->link->val);
 //convert(OCT, 0xdeadbeef);
 //draw_u();
 //}



//Author: Haoze Zhang
//u0904009


//*******************************Here is question answer***************************

//Question B1: What is the value of %cr4 at the start of _start before PSE is enabled?
//             What is its value afterward?(Answer with 32-bit hex values).(2 points)
//Answer:      The value of %cr4 is 0x00000000 before PSE is enabled.
//             Afterward, the value become 0x00000001
//Question B2: What is the address of the initial kernel stack that xv6 sets up (as a 32-bit hex value)? (1 point)
//Answer:      initial address is 0x0000e05b
//Question B3: I truncated the output in the last line of the above listing which includes the process's name
//             What is its name in xv6?(See if you can repeat the same steps and just grab it from gdb.) (2 points)
//Answer:      The name = "initcode\000\000\000\000\000\000\000"
//Question B4: Look through scheduler() in proc.c. What is the maximum number of processes that could exist
//             at once in xv6? Why - what xv6 data structure limits this? (4 points)
//Answer:      The maximum number of processes that could exist at once is 64, because the data structure
//             used in xv6 is intel x64 data structure, so that the maximum processer would be 64.
//Question B5: From the xv6 shell, trigger the breakpoint in exit and describe how you did it.
//             (To do this, think about when processes exit. Think about how you cause a process to created
//             and destroyed in UNIX to trigger the breakpoint.) (2 points)
//Answer:      In the xv6 shell, trigger the breakpoint in exit by typing in run after a prompt, 
//             for example, shell running and at a prompt $, type run which become $ run, breakpoint triggered. 
//Question B6: What state does a running process first change to after triggering an exit system call 
//             (that is, its status goes from RUNNING to what)? (Try to determine this by stepping through the code in exit()). (1 point)
//Answer:      state fron running to run failed
//Question B7: Use gdb to discover: what is the name and pid of the process that is exiting? And, what is the name and the pid of
//             the process that is the parent of the process that is exiting? (You may have trouble using
//             curproc in exit because the compiler optimized it out.  You can side step
//             that by using expressions that use myproc() directly. e.g. p myproc()). (4 points)
//Answer:      name: 1, pid: 3935. parent name: 2, ppid: 3928

//******************************question session end*******************************

uint64_t byte_sort(uint64_t arg)
{

  int i,j,minIndex;
  //divide number into array
  unsigned long a = (arg & 0xFF);
  unsigned long b = ((arg >> 8) & 0xFF);
  unsigned long c = ((arg >> 16) & 0xFF);
  unsigned long d = ((arg >> 24) & 0xFF);
  unsigned long e = ((arg >> 32) & 0xFF);
  unsigned long f = ((arg >> 40) & 0xFF);
  unsigned long g = ((arg >> 48) & 0xFF);
  unsigned long h = ((arg >> 56) & 0xFF);
  unsigned long  arr[8];
  unsigned long temp;
  arr[0] = a;
  arr[1] = b;
  arr[2] = c;
  arr[3] = d;
  arr[4] = e;
  arr[5] = f;
  arr[6] = g;
  arr[7] = h;
  //selection sort
  for(i = 0; i < 7; i ++){
    minIndex = i;
    for(j = i+1; j < 8; j ++){
      if(arr[j] < arr[minIndex]){
	minIndex = j;
      }
    }
    temp = arr[minIndex];
    arr[minIndex] = arr[i];
    arr[i] = temp;    
  }
  //swap
  temp = arr[0];
  arr[0] = arr[7];
  arr[7] = temp;
  temp = arr[1];
  arr[1] = arr[6];
  arr[6] = temp;
  temp = arr[2];
  arr[2] = arr[5];
  arr[5] = temp;
  temp = arr[3];
  arr[3] = arr[4];
  arr[4] = temp;
  uint64_t  w = 0;
  w = arr[7] + (arr[6]<<8)+(arr[5]<<16) + (arr[4]<<24) + (arr[3] << 32) + (arr[2] << 40)+(arr[1] << 48) + (arr[0] << 56);
  return w;
}
uint64_t nibble_sort(uint64_t arg)
{
  //divide number into array
  int x,y,minIndex;
  unsigned long a = (arg & 0xF);
  unsigned long b = ((arg >> 4) & 0xF);
  unsigned long c = ((arg >> 8) & 0xF);
  unsigned long d = ((arg >> 12) & 0xF);
  unsigned long e = ((arg >> 16) & 0xF);
  unsigned long f = ((arg >> 20) & 0xF);
  unsigned long g = ((arg >> 24) & 0xF);
  unsigned long h = ((arg >> 28) & 0xF);
  unsigned long i = ((arg >> 32) & 0xF);
  unsigned long j = ((arg >> 36) & 0xF);
  unsigned long k = ((arg >> 40) & 0xF);
  unsigned long l = ((arg >> 44) & 0xF);
  unsigned long m = ((arg >> 48) & 0xF);
  unsigned long n = ((arg >> 52) & 0xF);
  unsigned long o = ((arg >> 56) & 0xF);
  unsigned long p = ((arg >> 60) & 0xF);

  unsigned long  arr[16];
  unsigned long temp;
  arr[0] = a;
  arr[1] = b;
  arr[2] = c;
  arr[3] = d;
  arr[4] = e;
  arr[5] = f;
  arr[6] = g;
  arr[7] = h;
  arr[8] = i;
  arr[9] = j;
  arr[10] = k;
  arr[11] = l;
  arr[12] = m;
  arr[13] = n;
  arr[14] = o;
  arr[15] = p;
  //selection sort
  for(x = 0; x < 15; x ++){
    minIndex = x;
    for(y = x+1; y < 16; y ++){
      if(arr[y] < arr[minIndex]){
	minIndex = y;
      }
    }
    temp = arr[minIndex];
    arr[minIndex] = arr[x];
    arr[x] = temp;    
  }  
  uint64_t  w = 0;
  //recombine
  w = arr[0] + (arr[1]<<4)+(arr[2]<<8) + (arr[3]<<12) + (arr[4] << 16) + (arr[5] << 20)+(arr[6] << 24) + (arr[7] << 28)+ (arr[8] << 32)+ (arr[9] << 36)+ (arr[10] << 40)+ (arr[11] << 44)+ (arr[12] << 48)+ (arr[13] << 52)+ (arr[14] << 56)+ (arr[15] << 60);
  return w;
}

struct elt* str_to_list(const char* str)
{
  //the pointer
  struct elt* firstElement = NULL;
  struct elt* current = NULL;
  struct elt* previous = NULL;
  struct elt* next = NULL;
  firstElement = (struct elt*) malloc(sizeof(struct elt));
  
  //count is the length of str
  int count = 0;
  //we are assumed that at least one character
  while(str[count] !='\0'){
    count++;
  }

  if(firstElement == NULL){
    free(firstElement);
    return NULL;
  }
  firstElement -> val = str[0];
  if(count > 1){
    previous = firstElement;
  }
  //go through every items in str
  for(int i = 1; i < count; i ++){
      current = (struct elt*) malloc(sizeof(struct elt));
      //clear date if * == NULL
      if(current == NULL){
	while(firstElement != NULL){
	  next = firstElement ->link;
	  free(firstElement);
	  firstElement = next;
	}
      
	return NULL;
      }
      current -> val = str[i];
      previous ->link = current;
      previous = current;
  }
  return firstElement;
}


void convert(enum format_t mode, uint64_t value)
{
  //OCT
  if(mode == OCT){
  unsigned long  arr[22];
     for(int i = 0 ;i <  22; i ++) {     
       arr[i] = ((value >>(3* i)) & 0x7);
     }  
     for(int j = 0; j < 22; j ++){
       if(arr[21-j] == 0){
	 putc('0',stdout);
	 
       }else if(arr[21-j] == 1){
	 putc ('1',stdout);     
       }   
       else if(arr[21-j] == 2){
	 putc ('2',stdout);     
       }   
       else if(arr[21-j] == 3){
	 putc ('3',stdout);     
       }   
       else if(arr[21-j] == 4){
	 putc ('4',stdout);     
       }   
       else if(arr[21-j] == 5){
	 putc ('5',stdout);     
       }   
       else if(arr[21-j] == 6){
	 putc ('6',stdout);     
       }   
       else if(arr[21-j] == 7){
	 putc ('7',stdout);     
       }    

     }
     putc('\n', stdout);

  
  }
  //BIN
  else if (mode == BIN){
     unsigned long  arr[64];
     for(int i = 0 ;i <  64; i ++) {     
        arr[i] = ((value >> i) & 0x1);
     }  
     for(int j = 0; j < 64; j ++){
       if(arr[63-j] == 0){
	 putc('0',stdout);
	 
       }else
	 putc ('1',stdout);        
     }
     putc('\n', stdout);
  }
  //HEX
  else if (mode == HEX){
     unsigned long  arr[16];
     for(int i = 0 ;i <  16; i ++) {     
       arr[i] = ((value >>(4* i)) & 0xF);
     }  
     for(int j = 0; j < 16; j ++){
       if(arr[15-j] == 0){
	 putc('0',stdout);
	 
       }else if(arr[15-j] == 1){
	 putc ('1',stdout);     
       }   
       else if(arr[15-j] == 2){
	 putc ('2',stdout);     
       }   
       else if(arr[15-j] == 3){
	 putc ('3',stdout);     
       }   
       else if(arr[15-j] == 4){
	 putc ('4',stdout);     
       }   
       else if(arr[15-j] == 5){
	 putc ('5',stdout);     
       }   
       else if(arr[15-j] == 6){
	 putc ('6',stdout);     
       }   
       else if(arr[15-j] == 7){
	 putc ('7',stdout);     
       }   
       else if(arr[15-j] == 8){
	 putc ('8',stdout);     
       }   
       else if(arr[15-j] == 9){
	 putc ('9',stdout);     
       }   
       else if(arr[15-j] == 10){
	 putc ('a',stdout);     
       }   
       else if(arr[15-j] == 11){
	 putc ('b',stdout);     
       }   
       else if(arr[15-j] == 12){
	 putc ('c',stdout);     
       }    
      else if(arr[15-j] == 13){
	 putc ('d',stdout);     
       }   
      else if(arr[15-j] == 14){
	 putc ('e',stdout);     
       }   
      else if(arr[15-j] == 15){
	 putc ('f',stdout);     
       }   

     }
     putc('\n', stdout);
  }
}

void draw_u(void)
{
  int systemOpen = syscall(SYS_open, "./u.txt", O_WRONLY | O_CREAT, S_IRUSR | S_IXUSR );
  char u[] ="l      l\nl      l\nl      l\n l    l\n  1__1\n";
  int writeFile = syscall(SYS_write, systemOpen, u, sizeof(u)-1);
  if(writeFile < 0){
    syscall(SYS_close, systemOpen);
    syscall(SYS_unlink, "./u.txt");
    return;
  }
  int closeFile = syscall(SYS_close, systemOpen);
  if(closeFile < 0){
    return;
  }
}
