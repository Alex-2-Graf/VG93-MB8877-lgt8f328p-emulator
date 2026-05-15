	
  Ножка ВГ93                    Ножка lgt8f328р	
	1
	2	WR		PC4	27
	3	CS		PD2	32
	4	RD		PC5	28
	5	A0		PC2	25
	6	A1		PC3	26
	7	DB0		PB0	12
	8	DB1		PB1	13
	9	DB2		PB2	14
	10	DB3		PB3	15
	11	DB4		PB4	16
	12	DB5		PB5	17
	13	DB6		PB6	07
	14	DB7		PB7	08
	15	STEP		PC0	23
	16	DIR		PC1	24
	17	SL		---		
	18	SR		---
	19	CLR		PE3	22
	20	0V		GND	05
	
	21	+5V		VCC	04
	22	TEST		---
	23	HRDY		PE5	06
	24	CLC		PD4	02
	25	RSTB		---
	26	S		---
	27	RAWRD		PF4	03
	28	HLD		PD3	01
	29	TR43	0V	---
	30	WSTB		PE0	18
	31	WD		PD6	10
	32	CPRDY		PD1	31
	33	WF/DE		---
	34	TR00		PD0	30
	35	IP		PD5	09
	36	WRPT		PE2	21	
	37	DDEN		---
	38	DRQ		PD7	11
	39	INTRQ		PE1	19
	40
				PC6     29 reset подключить 0,1uf на землю и 10k на +5v			 


	Поддерживается только MFM кодирование
	DDEN   и  TEST не используется
	
	Неподдерживается предкомпенсация записи поэтому SL - 17 SR - 18  и TR43 - 29 надо подключить на землю
	Выходы   RSTB - 25 и WF/DE - 33 не поддерживаются

сделал выход WF/DE на 20 ноге контроллера пробуйте блокировку записи не делал если нужна пишите
	