# Predicting_Outcome_for_Bank_Telemarketing
An attempt at building classification model using the data available at https://archive.ics.uci.edu/ml/datasets/Bank+Marketing#  to predict the success in getting a customer to open a fixed term deposit 

## Abstract
Telemarketing	calls	require	a	lot	of	resources,	has	very	little	success	ratio,	and	can	be	annoying.	Banks	often	make	
such	telemarketing	calls	to	advertise	and	to	get	customers	to	subscribe	for	their	products.	This	project	aims	to	predict	
the	success	of	these	telemarketing	calls	using	the	data	available	from	UCI	Machine	Learning	Repository.	The	project	
uses	four	different	classification	models,	 compares	their	outcomes	and	provides	suggestion	on	model	to	be	used.	It	is	
found	that	either	Logistic	Regression	or	k-neighbors	classifier	can	be	used	depending	on	the	business	 needs.

## Motivation
Telemarketers	make	an	average	of	300-500	calls	in	an	eight-hour	day
- Banking	institutions	 are	no	exception
- Telemarketing	calls	are	annoying	when	we	receive	too	many	of	them

**What	if	we	can	predict	the	success	of	a	call?**
-  We	can	reduce	the	number	of	calls	by	calling	only	the	ones	 that	are	likely	to	subscribe
- This	means	less	calls	for	the	 telemarketer,	and	less	annoying	calls	for	the	people	who	might	not	be	interested	– a	win	win	situation	 that	saves	money	and	time	for	everyone	involved

## Results
| | Actual (test dataset) | Logistic Regression | k-Neighbors Classifer |
| --- | ---| --- | ---|
| **Total calls made** | 7622 | 1801 | 416 |
| **Success %** | 13.1% | 37.3% (~3 fold increase) | 66.1% (~5 fold increase) |
| **Total duration of all calls** | 549 hours | 130 hours (76% reduction) | 30 hours (94% reduction) |
| **# of customers or accounts gained** | 999 | 672 (32% loss) | 275 (75% loss) |

## Limitations
- Trade	off	between	accuracy	and	loss	in	customers
- Models	were	built	upon	an	imbalanced	dataset,	so	 the	appropriateness	 of	these	models can	be	questioned,	 but	can	be	addressed	as	more	data	is	collected

## Conclusions
**So	what	model	 to	use?**
- The	answer	depends	 on	various	other	factors.	Further	information	is	required	to	make	 this	decision.
  - Is	the	business	 trying	to	expand?
  - What's	the	long	term	benefit	 from	gaining	a	customer?	
  - Is	it	trying	to	save	money?	
  - Does	it	cost	more	in	telemarketing	for	100	hours	 than	it	costs	more	in	gaining	397	customers?	
  - Would	 the	business	 be	more	interested	in	not	making	unwanted	 telemarketing	calls	to	save	it's	image?
- An	appropriate	 response	 for	the	 first	two	questions	 might	require	a	Logistic	
Regression	 model,	where	as	a	focus	on	saving	money/time/image	 based	on	the	
answers	 to	the	last	 three	questions	 would	require	a	k-neighbors	classifier	 model
- Another possibility is to use k-neighbors classifier first where the probability of success is the highest, cover those customers and then move down the list to predictions from logistic regression 

