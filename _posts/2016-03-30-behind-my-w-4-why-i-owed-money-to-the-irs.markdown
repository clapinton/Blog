---
layout: post
title: Behind my W-4: Why I owed money to the IRS?
tags: w4, tax
---

>DISCLAIMER: I'm not an accountant. The knowledge I have came from reading instruction documents from the IRS itself. So DON'T hold me responsible if you end up in trouble. I suggest you take this as an intro and go research for yourself, specially if you think that your case is different in any way.

Let's talk about one of humanity's favorite subjects: taxes.

Recently, I received the following note from my accountant:
>Eric, sometimes my job is not kind. Unfortunately the deduction wasn't enough.

Yes, I owed money to the IRS. Again. The same thing happen in 2015, but now the debt was bigger (twice as big, to be exact). How the hell did this happen? I had changed my W-4 as my accountant instructed me in order to avoid owing money, and yet here I am, having to pay them again. Was it her fault? It had to be. She told me what to fill in and I did, trusting her judgement.

But maybe... it was my fault. For not understanding what had happened and figuring out a way to avoid that. And it was (past) time to correct that. I wanted to know how the system worked. What exactly was behind the W-4? Was it properly filled out? I read in a lot of places about "Put Married if this" and "Put Withhold at higher rate if that", but why? I don't like half-baked explanations, so I decided to learn it myself.

First of all: how much should I have paid?

## Calculating the expected annual federal contribution
This is done through the Federal Tax Brackets. There are two ways to calculate this: either through the <a href="https://www.irs.gov/pub/irs-pdf/i1040tt.pdf" target="_blank">form 1040tt</a> or through the actual bracket calculation. The difference is the 1040tt already has a bunch of values calculated for you in the form of a range, which means it will be off by a couple of dollars from the amount calculated using the brackets. If you want to do it manually and get the exact amount, you'll find a good calculator and explanation over at <a href="http://www.moneychimp.com/features/tax_brackets.htm" target="_blank">MoneyChimp</a>. For this exercise, we'll use the table.

To find this value, we must calculate the taxable income. If you open the <a href="https://www.irs.gov/pub/irs-pdf/f1040.pdf" target="_blank">form 1040</a>, you'll see it's pretty straightforward. Let's say our Adjusted Gross Income was $96k. We were filing jointly, so the Standard Deduction applied ($12,600 from line 40). Also, there were no dependents or exemptions to claim. This totals $83,400 of taxable income. From the table, that amounts to $12,431 in Federal Taxes, which was more than $1k above what we paid, according to our W-2.


## Calculating the expected annual state contribution
To do this, we go to the <a href="https://www.ftb.ca.gov/forms/2015/15_5402eztt.pdf" target="_blank">540-2EZ table</a>, using the same Adjusted Gross Income of $96k. From there, I see that I should have paid $3,107. Again, we underpaid by a little over $1k

## Why? WHY??
So now I know that I really owe money. So my question now is: where should that money have come from in the first place? Well, from my paycheck. It should have been withheld every month, as I specified on my W-4. Unless I drew a unicorn on my W-4. But the thing is, I didn't write "Please withhold $XXX,XX". I actually checked a box and wrote some small allowance number on it. So how does that become an amount in dollars? If I could find that out, I'd be able to calculate how much I told them to withhold, and then check if they actually did that.

## Calculating our Paycheck

This is how a paycheck gets calculated:

1. Start with your gross income (what you signed up for);
2. Add any bonuses you earned;
3. Subtract all pre-tax amounts, such as health and life insurances, FSA and retirement contributions (these are sometimes marked as "Excluded from federal taxable wages"). This results in your Federal Taxable Wages (FTW);
4. Subtract the federal, state, SS and other taxes (it doesn't matter the order in which you subtract);
5. The remainder is then given to you as your final income.


Some of these values are fixed amounts:
* the social security tax is a fixed 6.2% of the FTW (in 2016). That amount is correct for both of us.
* the same applies for the Medicare, @ 1.45% (for 2016), which is also correct.
The gross income is fixed and the bonus you earn depends on you. Pre-tax amounts also depends on what your company offers you and what you actually claimed, such as medical insurance and a 401k plan.

Then we get to the taxes. This is where your company looks at your W-4. You know, one of the documents you have to fill out every time you join a company as an employee.

![W-4 form fields](https://i.ytimg.com/vi/Dzal7kOgC64/maxresdefault.jpg)

### Calculating the State Taxes
In CA, we have the DE4, which is the same type of form. My wife and I have worked for some 5 companies already, and we had never heard of it. And the reason is simple, according to the EDD-CA:

>If the employee wants to claim a different marital status and/or different number of allowances for California Personal Income Tax (PIT) withholding, the employee must also complete a DE 4.

So all you need to really fill out is the W-4, which will be considered for both federal and state taxes. In any case, there are two ways of calculating the state tax, both described on the <a href="http://www.edd.ca.gov/pdf_pub_ctr/16methb.pdf" target="_blank">California Withholding Schedules</a>.

The instructions are pretty straightforward, so I won't go into details here. In the end, I noticed that both our state taxes were under-withheld (mine was actually much worse). That's two red flags already. One of my wife's colleagues actually mentioned that she usually ends up owing state taxes, but never as much as we owed this year.

### Calculating the Federal Taxes

This amount comes from a table on <a href="https://www.irs.gov/pub/irs-pdf/p15.pdf" target="_blank">IRS's Publication 15, Circular E - Employer's Tax Guide (2016)</a> (notice that the pages mentioned here might change on other years). It takes into account your taxable income, number of withholding allowances, civil status and frequency of payment.

Start off by taking the number of claimed allowances (box 5 from W-4) and multiply it by the allowance amount for that year, depending on the frequency of payment (page 42 of Publication 15, in 2016). Subtract the result from the taxable income.

Take your new amount and use the Percentage Method Tables (page 44) to get to the final formula to calculate your federal tax that will be withheld. So if you are married and you end up with a FTW of $3,675 on a monthly basis, claiming 2 allowances, that means you should pay:

1. Subtract the two allowances: `$3,675 - 2x($337.50) = $3,000`

2. Use the new value to find the formula on the table: `$154.50 + 15%($3,000 - $2,258) = $154.50 + $111.30 = $265.70`

If you want to check your calculations, you can use the Wage Bracket Tables. In our case, page 61 tells us the value is $264. Keep in mind that the wage brackets method numbers are calculated for ranges (between $3640 and $3680), so the value might not match exactly, but it should always be within a couple of dollars. If the difference gets to two digits, you've done something wrong with the formula.

>Note: Biweekly means every two weeks, while Semimonthly means twice per month. They are not the same!! I know it seems obvious, but it's easy to go with the biweekly table when you get paid every 15 days.

Last, but not least, subtract any amount that you have on Box 6.

Now you know how much you have to pay the IRS on each paycheck. Now grab your pay stub and check how much your employer has been withholding. It's really important to make sure this is correct. REALLY important. Because, once again, my taxes were under-withheld (my wife's were ok).

## The Fuck Up
It turns out that both state AND federal value were wrong on my pay stub, while only my wife's state was messed up, although by a small amount. So now I was getting closer to the truth: my paycheck was the problematic one. I called up the financial guys from my company and asked why they were withholding less than what I told them to.

The answer was a weird one: there was a check on my payroll to overwrite whatever amount was calculated through the W-4 data. According to the lady there, it's worse this way, since they have to manually calculate stuff, so they prefer to leave it in auto mode. For some reason, someone marked that little box on my account and input a new number, just because.

Ok, so who did it? And most importantly: why?

Well, this I'll never know. My paycheck was processed by another lady who had left the company. The new lady I was talking to was just following in the footsteps.

So there you have it: mystery solved. Now on to solve the mystery of how I'll be paying my debt...

## Lesson learned
Always, ALWAYS check your pay stubs. If not every month, every other month. Make sure the correct amount is getting withheld. Even if it is for 3 straight months, who knows when a new person takes over your paycheck and changes some number for no apparent reason. Seems like a long shot, but I'm not willing to risk it when it comes to my money. Besides, it's as simple as looking at a number and checking if it matches what you had previously calculated.

Also, estimate your liability at the beginning of the year. Take your income from the previous year and apply the current years'  tables. If you're having a baby or buying a house, your taxable income will change, so calculate accordingly. After you have the amount of tax you should pay, check if whatever's written on your W-4 will cover that. If not, change it. It's free and you can do it anytime during the year.

Needless to say, I'm now managing our taxes by myself, without the accountant. Not that it was her fault, but the fact is: she would have never found out about this, since it would require some digging, which would require time, which is what an accountant barely has, specially during tax season.