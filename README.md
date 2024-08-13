
# REATAIL TRANSACTION project

# PROBLEM STATEMENT

This is a dataset  containing retail transaction from a large retailer,with over 100 thousand records spanning 2 years.
Each represents a single transaction and includes features such as:

- Customer ID (Anonymous)
- Product ID
- Quantity
- Price
- Transaction dataset
- Discount Applied
- Payment Method
- Store Location etc.

My goal is to analyze this dataset to determine:

1. The Total Amount by Day Name
2. The Total Amount by Month Name
3. The Total Amount Quarterly
4. The Total Amount Yearly
5. The Total Number of Product Sold
6. The Total Amount of Discount Applied for each Payment Method

# LIBRARY USED
1. Matplotlib
2. Pandas
3. Numpy

# STEPS

- Rounding up the TotalAmount column to a nearest decimal place.Retail_Money["TotalAmount"]=Retail_Money["TotalAmount"].round()
- Converting the TransactionDate column from an object to date time type.Retail_Money["TransactionDate"]=pd.to_datetime(Retail_Money["TransactionDate"])

1. TOTAL AMOUNT BY DAY NAME 
- Retail_Money["Day_Name"]=Retail_Money["TransactionDate"].dt.day_name()
- Day=Retail_Money.groupby("Day_Name")["TotalAmount"].sum()  
- Day
- Name=Day.index
- Numbers=Day.values
- plt.bar(Name,Numbers,color="Red")
- plt.title("TRANSACTION PER DAY",fontsize=16,fontweight="bold",fontstyle="italic")
- plt.xlabel("Name of day")
- plt.ylabel("Number per day")
- plt.savefig("TRANSCATION PER DAY.png")
- plt.show()
  
![TRANSCATION PER DAY](https://github.com/user-attachments/assets/cb16fbb2-e598-43f5-9608-7674e52ff70c)

2. TOTAL AMOUNT BY MONTH NAME 
- Retail_Money["Month_name"]=Retail_Money["TransactionDate"].dt.month_name()
- Month=Retail_Money.groupby("Month_name")["TotalAmount"].sum().round()
- Month
- Name1=Month.index
- Numbers1=Month.values
- plt.pie(Numbers1,labels=Name1)
- plt.title("TRANSACTION PER MONTH",fontsize=16,fontweight="bold",fontstyle="italic")
- plt.savefig("TRANSACTION PER MONTH.png")
- plt.show()
  
![TRANSACTION PER MONTH](https://github.com/user-attachments/assets/15e1858a-26de-4c5f-8361-3e00f3546b04)

3. TOTAL AMOUNT BY QUARTER 
- Retail_Money["Quarter"]=Retail_Money["TransactionDate"].dt.quarter
- Qtr=Retail_Money.groupby("Quarter")["TotalAmount"].sum().round()
- Qtr
- Name2=Qtr.index
- Number2=Qtr.values
- plt.barh(Name2,Number2,color="Red")
- plt.title("TRANSACTION PER QUARTER",fontsize=16,fontweight="bold",fontstyle="italic")
- plt.xlabel("Number per Qtr")
- plt.ylabel("count per Qtr")
- plt.savefig("TRANSACTION PER QUARTER.png")
- plt.show()
  
![TRANSACTION PER QUARTER](https://github.com/user-attachments/assets/b4b41803-43a2-475c-88ea-96153e173e49)

4. TOTAL AMOUNT YEARLY 
- Retail_Money["Year"]=Retail_Money["TransactionDate"].dt.year
- Year=Retail_Money.groupby("Year")["TotalAmount"].sum().round()
- Year
- Name3=Year.index
- Name3=Year.index
- plt.barh(Name3,Number3,color="Red")
- plt.title("TRANSACTION PER YEAR",fontsize=16,fontweight="bold",fontstyle="italic")
- plt.xlabel("Number per Year")
- plt.ylabel("count per Year")
- plt.savefig("TRANSACTION PER YEAR.png")
- plt.show()
  
![TRANSACTION PER YEAR](https://github.com/user-attachments/assets/a45ba4a5-3b8b-4f03-8c8e-5c065b9bdc58)

5. TOTAL NUMBER OF PRODUCT SOLD 
- ProductCategory=Retail_Money.groupby("ProductCategory")["TotalAmount"].count()
- ProductCategory
- Name4=ProductCategory.index
- Number4=ProductCategory.values
- plt.pie(Number4,labels=Name4,shadow=True,autopct="%1.0f%%",explode=[0.1,0.1,0,0])
- plt.title("TOTAL NUMBER OF PRODUCT CATEGORY SALES",fontstyle="italic",fontweight="bold",fontsize=12,c="RED")
- plt.savefig("TRANSACTION NUMBER OF PRODUCTS SOLD.png")
- plt.show()
  
![TRANSACTION NUMBER OF PRODUCTS SOLD](https://github.com/user-attachments/assets/1f8c447c-4582-41cd-be6a-20a80b3a31b8)

6. TOTAL AMOUNT OF DISCOUNT APPLIED FOR EACH PAYMENT METHOD  
- Payment=Retail_Money.groupby("PaymentMethod")["DiscountApplied(%)"].sum()
- Payment
- Name5=Payment.index
- Number5=Payment.values
- plt.plot(Name5,Number5,marker="+")
- plt.title("DISCOUNT APPLIED FOR EACH PAYMENT METHOD",fontsize=10,fontstyle="oblique",fontweight="bold",c="b")
- plt.xlabel("payment Method")
- plt.ylabel("Discount Applied(%)")
- plt.savefig("DISCOUNT APPLIED FOR EACH PAYMENT METHOD.png")
- plt.show()
  
![DISCOUNT APPLIED FOR EACH PAYMENT METHOD](https://github.com/user-attachments/assets/ddb4c536-bf9b-4959-9049-0f0d1b902b66)


# SCREENSHOT OF THE CHART IN SUBPLOT
- fig,Cash_Money=plt.subplots(nrows=2,ncols=3,figsize=(14,8))
- fig.suptitle("RETAIL TRANSACTION MODE",fontsize=45,fontstyle="italic",fontweight="bold",c="r")
- Cash_Money[0,0].bar(Name,Numbers,color="Red")
- Cash_Money[0,1].plot(Name1,Numbers1,marker="o")
- Cash_Money[0,2].pie(Number2,labels=Name2,autopct="%1.0f%%",shadow=True,explode=[0,0.1,0,0.1])
- Cash_Money[1,0].bar(Name3,Number3,color="orange")
- Cash_Money[1,1].pie(Number4,labels=Name4,shadow=True,autopct="%1.0f%%",explode=[0.1,0.1,0,0])
- Cash_Money[1,2].plot(Name5,Number5,marker="+")
- Cash_Money[0,0].set(title="TRANSACTION PER DAYNAME")
- Cash_Money[0,1].set(title="TRANSACTION PER MONTHNAME")
- Cash_Money[0,2].set(title="TRANSACTION PER QUARTER")
- Cash_Money[1,0].set(title="TRANSACTION PER YEAR")
- Cash_Money[1,1].set(title="TOTAL NUMBER OF PRODUCT CATEGORY SALES")
- Cash_Money[1,2].set(title="DISCOUNT APPLIED FOR EACH PAYMENT METHOD")
- plt.tight_layout()
- plt.savefig("SCREENSHOT OF THE CHART IN SUBPLOT.png")
- plt.show()
  
![SCREENSHOT OF THE CHART IN SUBPLOT](https://github.com/user-attachments/assets/e0058083-3340-4c03-8c31-03e56b5a0792)














