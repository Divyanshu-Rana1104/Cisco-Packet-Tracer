	



FCFS


/*
 * FCFS Scheduling Program in C
 */
 
#include <stdio.h>
int main()
{
    int pid[15];
    int bt[15];
    int n;
    printf("Enter the number of processes: ");
    scanf("%d",&n);
 
    printf("Enter process id of all the processes: ");
    for(int i=0;i<n;i++)
    {
        scanf("%d",&pid[i]);
    }
 
    printf("Enter burst time of all the processes: ");
    for(int i=0;i<n;i++)
    {
        scanf("%d",&bt[i]);
    }
 
    int i, wt[n];
    wt[0]=0;
 
    //for calculating waiting time of each process
    for(i=1; i<n; i++)
    {
        wt[i]= bt[i-1]+ wt[i-1];
    }
 
    printf("Process ID     Burst Time     Waiting Time     TurnAround Time\n");
    float twt=0.0;
    float tat= 0.0;
    for(i=0; i<n; i++)
    {
        printf("%d\t\t", pid[i]);
        printf("%d\t\t", bt[i]);
        printf("%d\t\t", wt[i]);
 
        //calculating and printing turnaround time of each process
        printf("%d\t\t", bt[i]+wt[i]);
        printf("\n");
 
        //for calculating total waiting time
        twt += wt[i];
 
        //for calculating total turnaround time
        tat += (wt[i]+bt[i]);
    }
    float att,awt;
 
    //for calculating average waiting time
    awt = twt/n;
 
    //for calculating average turnaround time
    att = tat/n;
    printf("Avg. waiting time= %f\n",awt);
    printf("Avg. turnaround time= %f",att);
}





// C implementation of First - Fit algorithm 
#include<stdio.h> 

// Function to allocate memory to 
// blocks as per First fit algorithm 
void firstFit(int blockSize[], int m, int processSize[], int n) 
{ 
	int i, j; 
	// Stores block id of the 
	// block allocated to a process 
	int allocation[n]; 

	// Initially no block is assigned to any process 
	for(i = 0; i < n; i++) 
	{ 
		allocation[i] = -1; 
	} 
	
	// pick each process and find suitable blocks 
	// according to its size ad assign to it 
	for (i = 0; i < n; i++)	 //here, n -> number of processes 
	{ 
		for (j = 0; j < m; j++)	 //here, m -> number of blocks 
		{ 
			if (blockSize[j] >= processSize[i]) 
			{ 
				// allocating block j to the ith process 
				allocation[i] = j; 

				// Reduce available memory in this block. 
				blockSize[j] -= processSize[i]; 

				break; //go to the next process in the queue 
			} 
		} 
	} 

	printf("\nProcess No.\tProcess Size\tBlock no.\n"); 
	for (int i = 0; i < n; i++) 
	{ 
		printf(" %i\t\t\t", i+1); 
		printf("%i\t\t\t\t", processSize[i]); 
		if (allocation[i] != -1) 
			printf("%i", allocation[i] + 1); 
		else
			printf("Not Allocated"); 
		printf("\n"); 
	} 
} 

// Driver code 
int main() 
{ 
	int m; //number of blocks in the memory 
	int n; //number of processes in the input queue 
	int blockSize[] = {100, 500, 200, 300, 600}; 
	int processSize[] = {212, 417, 112, 426}; 
	m = sizeof(blockSize) / sizeof(blockSize[0]); 
	n = sizeof(processSize) / sizeof(processSize[0]); 

	firstFit(blockSize, m, processSize, n); 

	return 0 ; 
} 






// C++ implementation of Best - Fit algorithm 
#include<iostream> 
using namespace std; 

// Method to allocate memory to blocks as per Best fit algorithm 
void bestFit(int blockSize[], int m, int processSize[], int n) 
{ 
	// Stores block id of the block allocated to a process 
	int allocation[n]; 

	// Initially no block is assigned to any process 
	for (int i = 0; i < n; i++) 
		allocation[i] = -1; 

	// pick each process and find suitable blocks 
	// according to its size ad assign to it 
	for (int i = 0; i < n; i++) 
	{ 
		// Find the best fit block for current process 
		int bestIdx = -1; 
		for (int j = 0; j < m; j++) 
		{ 
			if (blockSize[j] >= processSize[i]) 
			{ 
				if (bestIdx == -1) 
					bestIdx = j; 
				else if (blockSize[bestIdx] > blockSize[j]) 
					bestIdx = j; 
			} 
		} 

		// If we could find a block for current process 
		if (bestIdx != -1) 
		{ 
			// allocate block j to p[i] process 
			allocation[i] = bestIdx; 

			// Reduce available memory in this block. 




// C++ program to demonstrate
// FCFS Disk Scheduling algorithm
#include <stdio.h>
#include <math.h>

int size = 8;

void FCFS(int arr[],int head)
{
	int seek_count = 0;
	int cur_track, distance;

	for(int i=0;i<size;i++)
	{
		cur_track = arr[i];
	
		// calculate absolute distance
		distance = fabs(head - cur_track);
	
		// increase the total count
		seek_count += distance;
	
		// accessed track is now new head
		head = cur_track;
	}

	printf("Total number of seek operations: %d\n",seek_count);
	
	// Seek sequence would be the same
	// as request array sequence
	printf("Seek Sequence is\n");

	for (int i = 0; i < size; i++) {
		printf("%d\n",arr[i]);
	}
}

//Driver code
int main()
{
	// request array
	int arr[8] = { 176, 79, 34, 60, 92, 11, 41, 114 };
	int head = 50;
	
	FCFS(arr,head);

	return 0;
}

//This code is contributed by Pratham Kashyap




sstf

#include<stdio.h>
#include<stdlib.h>
int main()
{
    int RQ[100],i,n,TotalHeadMoment=0,initial,count=0;
    printf("Enter the number of Requests\n");
    scanf("%d",&n);
    printf("Enter the Requests sequence\n");
    for(i=0;i<n;i++)
     scanf("%d",&RQ[i]);
    printf("Enter initial head position\n");
    scanf("%d",&initial);
    
    // logic for sstf disk scheduling
    
        /* loop will execute until all process is completed*/
    while(count!=n)
    {
        int min=1000,d,index;
        for(i=0;i<n;i++)
        {
           d=abs(RQ[i]-initial);
           if(min>d)
           {
               min=d;
               index=i;
           }
           
        }
        TotalHeadMoment=TotalHeadMoment+min;
        initial=RQ[index];
        // 1000 is for max
        // you can use any number
        RQ[index]=1000;
        count++;
    }
    
    printf("Total head movement is %d",TotalHeadMoment);
    return 0;
}

