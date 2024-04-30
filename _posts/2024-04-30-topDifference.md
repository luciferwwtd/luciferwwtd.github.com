---
layout: post
title:  "하노이 탑(실습)"
date:   2024-04-30
excerpt: ""
tag:
- example
comments: true
---

# 예제 코드 1
    public class HanoiTopV1 {
    	static void hanoi(int n, int from, int by, int to) {
    	    if(n==1){
    	    	System.out.printf("%d -> %d\n", from, to);
    	    }
    		else {
    			hanoi(n-1, from, to, by);		//	1 -> 2, by 3
    			System.out.printf("%d -> %d\n", from, to);
    			hanoi(n-1, by, from, to);		//	2 -> 3, by 1
    		}
        }
    }
	
	public static void main(String[] args) {
    		hanoi(3, 1, 2, 3);
    	}
    }

# 예제 코드 2

    public class HanoiTopV2 {
	
    	final static int TOPHEIGHT = 9;
    	final static int TOPWIDTH = 9;
    	final static int BLOCKHEIGHT = 3;
	
    	char TOP[][] = {


			{0x00, 0x00, 0x01, 0x06, 0x06, 0x06, 0x02, 0x00, 0x00},
			{0x00, 0x00, 0x05, 0x00, 0x53, 0x00, 0x05, 0x00, 0x00},
			{0x00, 0x00, 0x03, 0x06, 0x06, 0x06, 0x04, 0x00, 0x00},

			{0x00, 0x01, 0x06, 0x06, 0x06, 0x06, 0x06, 0x02, 0x00},
			{0x00, 0x05, 0x00, 0x00, 0x4D, 0x00, 0x00, 0x05, 0x00},
			{0x00, 0x03, 0x06, 0x06, 0x06, 0x06, 0x06, 0x04, 0x00},

			{0x01, 0x06, 0x06, 0x06, 0x06, 0x06, 0x06, 0x06, 0x02},
			{0x05, 0x00, 0x00, 0x00, 0x42, 0x00, 0x00, 0x00, 0x05},
			{0x03, 0x06, 0x06, 0x06, 0x06, 0x06, 0x06, 0x06, 0x04}


		};


    	char PAGE[][];
	
    	HanoiTopV2(){
    		PAGE = new char[TOPHEIGHT][TOPWIDTH*BLOCKHEIGHT];
    		for(int indexx=0; indexx < TOPHEIGHT; indexx++){
    			for(int indexy=0; indexy < TOPWIDTH*BLOCKHEIGHT; indexy++){
    				PAGE[indexx][indexy] = 0x00;
    			}
    		}
    	}
	

    	void pageInit()
    	{
    		for(int i=0; i<TOPHEIGHT; i++){
    			for(int j=0; j<TOPWIDTH; j++){
    				PAGE[i][j] = TOP[i][j];
    			}
    		}
    	}

	
        void graphicsCopy(int from, int to) {
    		from = (from-1)*9;
    		to = (to-1)*9;
    		int count = 0;

    		for(int i=0; i<TOPHEIGHT-1; i=i+BLOCKHEIGHT){

    			if((PAGE[i][from+(TOPWIDTH/2)] != 0x00)&&(PAGE[i+2][from+(TOPWIDTH/2)] != 0x00)) {

    				for(int jj=TOPHEIGHT-BLOCKHEIGHT; 0<=jj; jj=jj-BLOCKHEIGHT) {
    					if((PAGE[jj][to+(TOPWIDTH/2)] == 0x00)&&(PAGE[jj+2][to+(TOPWIDTH/2)] == 0x00)) {
				
    						for(int j=0; j<TOPWIDTH; j++){

    							for(int block=0; block<BLOCKHEIGHT; block++){
    								char tmp = PAGE[i+block][j+from];
    								PAGE[i+block][j+from] = PAGE[jj+block][j+to];
    								PAGE[jj+block][j+to] = tmp;
    								++count;
    							}
    						}
    					}

    					if(count==(TOPWIDTH*BLOCKHEIGHT))
    						return;
    				}
    			}
    		}
    	}
	
    	void gidungGraphic() {
    		System.out.printf("%5s%9s%9s\n", "1", "2", "3");
    	}
	
    	void topGraphics() {
    		for(int i=0; i<TOPHEIGHT; i++){
    			for(int j=0; j<TOPWIDTH*BLOCKHEIGHT; j++){
    				System.out.printf("%c", PAGE[i][j]);
    			}
    			System.out.println();
    		}
    	}
	

    	void move(int from, int to) {
    		try {
    			Thread.sleep(1000);
    		} catch (InterruptedException e) {
    			// TODO Auto-generated catch block
    			e.printStackTrace();
    		}

    		graphicsCopy(from, to);

    		topGraphics();

    		gidungGraphic();

    		System.out.printf("\n no.%d pillar to  no.%d pillar\n\n", from, to);
    	}
	
    	void recursive(int n, int from, int by, int to) {
    	    if(n==1)
    			move(from, to);

    		else
    		{
    			recursive(n-1, from, to, by);
    			move(from, to);
    			recursive(n-1, by, from, to);
    		}
    	}
	
	
    	public static void main(String[] args){
    		HanoiTopV2 hanoi = new HanoiTopV2();
    		hanoi.pageInit();
    		hanoi.topGraphics();
    		hanoi.gidungGraphic();

    		System.out.println("Shall we draw the Hanoi Tower?");

    		try {
    			Thread.sleep(1000);
    		} catch (InterruptedException e) {
    			// TODO Auto-generated catch block
    			e.printStackTrace();
    		}

    		hanoi.recursive(BLOCKHEIGHT, 1, 2, 3);

    		System.out.println("Hanoi Tower success!");
    	}
    }