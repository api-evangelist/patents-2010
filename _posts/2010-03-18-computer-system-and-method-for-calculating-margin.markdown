---

title: Computer system and method for calculating margin
abstract: The present invention relates to a computer system, computerized method and computer program product for calculating margin requirements in a more efficient way. In particular it relates to margin calculations for being used by clearing house in order to optimize calculation of margin requirements.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08548894&OS=08548894&RS=08548894
owner: OMX Technology AB
number: 08548894
owner_city: Stockholm
owner_country: SE
publication_date: 20100318
---
This application claims priority to U.S. Provisional Application No. 61 220 087 filed Jun. 24 2009 the entire contents of which is hereby incorporated by reference.

The present invention relates to margin calculations associated with computerized market places. In particular it relates to a computer system and method for calculating optimal margin requirements in clearing systems.

Computerized market places have in the last few years undergone major changes and a lot of money has been invested in research and development in order to improve the systems. However even though the current systems in use are very sophisticated there exist needs to even further improve computerized systems associated with computerized market places. The computer systems associated with computerized market places are for example the central exchange system where the actual matching of orders takes place clearing and settlement systems for handling post trade activities and trading systems that are the systems that traders uses in order to send in orders to the central exchange system.

In order to trade different financial instruments such as stocks options futures forwards and so forth the members connected to the market place must typically be associated with at least one clearing account in a clearing house that keeps collateral. The reason for this is that the clearinghouse works as an intermediary between the seller and the buyer and in order to avoid that any one of the parties of a trade defaults so that an agreed trade can not be executed the clearinghouse needs collateral stored in an account. Usually this collateral is stored in a margin account and can be divided into initial margin and variation margin. The initial margin shall cover heavy market movements of the positions and the variation margin is the positions accumulated profit and loss which is typically subject to a daily mark to market. The initial margin can be calculated using different positions in different financial instruments and by netting positions.

A problem that the clearing houses are facing is the issue of making sure that there is enough initial margin in order to cover heavy market movements for a desired number of lead days but also that the margin requirement is not over conservative since this will restrain the market.

Commercial available margin models such as SPAN OMS II and TIMS calculate initial margin per contract. Correlations between these contracts are handled differently between these models but in general all are ill suited for markets that exhibit very strong correlation. Furthermore calculating initial margin per contract is not optimal for certain instruments such as FX forwards and interest swaps since the total risk can be closed out by a combination of several different contracts. Calculating initial margin per contract will therefore give over conservative margin requirements for these types of portfolios.

It is a further object of the present invention to provide a solution that is able to handle multi currency products within the same margin system run.

It is a further object of the present invention to provide a solution that is able to calculate an optimal margin requirement for instrument positions in an account.

It is a further object of the present invention to provide a solution that is able to calculate an optimal margin requirement for an account associated with FX forwards.

It is a further object of the present invention to provide a solution that is able to calculate an optimal margin requirement for an account associated with interest rate swaps.

It is a further object of the present invention to provide a solution that is able to calculate an optimal margin requirement for an account associated with multiple instrument types.

It is a further object of the present invention to provide a solution that is able to netting contracts in a new way.

At least one of the above objects is obtained by the present invention as set out in the appended claims.

According to a first aspect of the invention this is achieved by a computer system for calculating margin requirements the computer system comprising

wherein the computer system is configured such that the processor divides the contracts in the memory into cash flows.

Letting the computer system break up the individual contracts into cash flows has the advantage that margin amounts can be lowered without being less conservative when managing the risk of e.g. a clearing house.

In one embodiment the computer system can be configured to netting the different cash flows of a contract against other cash flows of other contracts. This has the advantage that a more optimal margin requirement can be achieved.

Furthermore the computer system further can be configured to treat each cash flow separately. This has the advantage that a more flexible system can be obtained.

In another embodiment the computer system can further be configured to net currency exposures across future value dates for the cash flows of the contracts. This has the advantage that margin can be calculated on contracts and or positions having a risk exposure.

In one embodiment the computer system is configured to handle multi currency products within the same margin system run.

The computer system can be a computer system configured such that it can be used for a clearing house computer system.

In accordance with second aspect of the invention the above object is obtained by a computerized method for calculating margin requirements implemented on a computer system the computer system comprising a memory comprising contracts and a processor associated with the memory the method comprising the steps of 

By letting the computerized method breaking up the individual contracts into cash flows has the advantage that margin amounts can be lowered without being less conservative when managing the risk of e.g. a clearing house.

By concentrating the calculations on sub parts of the contracts the quite cumbersome set up of a correlation structure in the existing margin models can be avoided. This will facilitate the understanding and acceptance of the model both externally and internally for e.g. a clearing house.

In a third aspect of the invention the above object is obtained by a computer program product according to any of the previous described embodiments the computer program product being stored on a data carrier.

These and other aspects of the invention will be apparent from and elucidated with reference to the embodiments described hereinafter.

FX forwards are different than stock forwards since they will always result in cash flows in two directions. This is because one currency is always exchanged for another currency. There are two main requirements on a margin model for FX forwards firstly the margin model must give enough margins i.e. the margin requirement shall contain the portfolio s accumulated profit and loss plus additional margin to cover heavy market movements for the desired number of lead days. Secondly the margin model must consider the portfolio as a whole. This implies that the model shall net between several positions that combined closes the future payments in one currency.

A FX Outright Forward is an agreement to at the value date exchange an amount of the fixed currency for an amount of the variable currency to a contracted exchange rate. The name convention is Fixed Currency Variable Currency. The variable currencies are USD EUR and NOK in the examples below.

A Spot FX is a FX Outright Forward with value date t T 2. Here T stands for the trading date of the Spot FX contract.

A FX swap can always be broken up into two FX forward contracts. The forwards contracts can further be broken up as described later in this document.

For bought Spot FX contracts and bought FX Outright Forward contracts the profit and loss expressed in the variable currency of the FX pair on day t is calculated according to Equation 2.

For sold Spot FX contracts and sold FX Outright Forward contracts the profit and loss PnL expressed in the variable currency of the FX pair on day t is calculated according to Equation 3. CR Fix 3 

The present value in a given currency of a future payment in the same currency is calculated according to Equation 4.

The exchange rates for all currency pairs are usually not independent of each other. In order to avoid an arbitrage situation Equation 5 must be fulfilled.

According to a prior art margin method such as the OMS II method the margin requirement is calculated per position. Further with the prior art margin methods it is currently only technically possible to define a market with one currency. Hence with the prior art margin method OMS II one FX market would have to be defined per variable currency. All relevant currencies could later be defined as underlying instruments in each FX market as described by the example below.

OMS II would only be able to handle correlation within one currency. Hence OMS II will give over conservative margin requirements for portfolios that have netted their future payments by buying and selling several positions with different variable currencies for example bought USD JPY bought EUR USD and sold EUR JPY .

The present invention solves this problem. The computer implemented margin calculation method NOMX CFM of the present invention preferably calculates the initial margin per currency. This procedure is to divided into the steps described below.

A variation margin will be calculated per position and this will be equal to that position s PnL calculated according to Equation 2 and Equation 3. If desired it will be possible to perform net present value calculations of the PnLs when calculating the variation margin.

The total variation margin for one account will be the sum of the PnLs for all positions in that account. The total variation margin will be given per currency.

List all future cash flows in a table were the columns represent the currency and the rows represent the value date. This table is called the Cash Flow Table refer to Table 1 . Positive and negative payments on the same value date and in the same currency will be netted in this step.

It should be noted that the closing fixing rates will be used when the FX contracts are fit into the Cash Flow Table. The market value of the future payments in the Cash Flow Table will therefore be equal to zero.

A new row is created in the Cash Flow Table. Each column in this row contains the net present value NPV of the future cash flows in that currency. If no interest rate shifts are considered the present values will be calculated using Equation 4. For most currencies the present value calculations will only be performed to T 2. This is because the closing fixing rates will be spot rates and hence most of the times have value date T 2. The number of days that the present value calculations are performed to will be configurable in the system

For FX Outright Forwards there is a risk related to shifts in the interest rate curves. This risk is accounted for in NOMX CFM by simulating different shifts in the interest rate curves. NOMX CFM is flexible and each exchange may choose their own way to stress the yield curves. This text present three different methods to stress the yield curve. In the preferred embodiment of the present invention NOMX CFM the interest rate shifts will be performed by the Rolling Value Method .

In this method a number of actual yield curve shifts between an appropriate numbers of days are stored in a database let us say 500 days for the discussion . One way of doing this is to calculate the percentage shift for each day in the interest rate curves and store that number. When the NPV are to be calculated the interest rate curve of today is shifted in the 500 possible different ways and Equation 4 is used to calculate a NPV per currency. The interest rate curve that produces the lowest NPV would then be used and that would also be the NPV to use as the margin figure.

The advantage is that the correlation pattern of the past 500 days is automatically included in the calculations 

In this method the movements of the interest rate curves are analyzed and the largest independent movements are identified. For most markets this is

Since these movement generally explain most of the movement of an interest rate curve these factors can be used to calculate margins with a reasonable amount of confidence. The different movements are independent of each other which mean that one can calculate margins by having parameters define each movement. When the NPV are to be calculated the interest rate curves of today are shifted according to their principal components and Equation 4 is used to calculate a NPV per currency. The interest rate curve that produces the lowest NPV would then be used and that would also be the NPV to use as the margin figure.

The yield curves will always look reasonable no spikes or saw tooth shapes . It will be possible to introduce correlation between yield curves in different currencies with this method.

In this method the swap forward curve is shifted in a rolling fashion starting with the cash flow furthest away.

The rolling value method is robust and it will find the worst possible interest rate curves for the portfolio. The yield curves will show periods with increased numbers and periods with decreased number depending on the complete portfolios exposure. It will be possible to stress the less liquid and or more volatile parts of the yield curves with a higher risk parameter compared to the interest rate curves more liquid and or less volatile parts. It will be straight forward to introduce correlation between different interest rate curves in the same currency.

A scanning range parameter is applied to all net present valued payments. The scanning range parameter should be expressed in percentage and it shall cover market movements of the currency compared to the account s base currency for the desired number of lead days.

The scanning range parameter is applied on the spot fixing exchange rate of the given currency compared to the base currency of the account in conjunction with converting the net present value in that currency to the base currency of the account. The scanning range parameter shall be applied according to Equation 8 Equation 9 .

It will be possible to consider correlation between different currencies in this step. This will be applied through the window method which is the same algorithm as is used in OMS II to account for correlation benefits between different underlying instruments.

Since the market value for the future payments in the Cash Flow Table is equal to zero the initial margin i.e. the margin added by the risk parameters is equal to the sum of all converted net present cash flows. Initial margin P 10 

The variation margin contains the PnL of all FX contracts accumulated as a netted variation margin amount from all positions no matter of their value date. This might not be suitable for future styled customers since part of their pledged collateral might be used for settlement at the value date.

It will therefore be possible to incorporate a FX settlement margin to NOMX CFM. The FX settlement margin is preferably defined per currency and it is equal to the total losses in that currency for all positions with value date less than T a configurable amount of days. If FX settlement margin is used then it may be pledged preferably as cash in the relevant currencies.

The margin requirement may be covered with any collateral approved by the market place such as cash or any type securities may be used.

It should be noted that for participants that are configured to use FX settlement margin the margin presentation and collateral handling may be different.

One fundamental prerequisite for absorbing counterparty risk in a clearing house is the ability to price all positions of the counterparts to the clearing house. In very general terms the price server is a market maker computer application that collects information over a computer network from various price sources such as from other computerized exchanges banks and from other information server systems. Information regarding derivatives equities interest rate deals and so forth may be collected and with these building blocks the price server is able to construct best effort pricing of other less liquid or even non traded instruments.

According to a preferred embodiment of the present invention the price handling will be needed in order to be able to calculate accurate variation margin as well as initial margin.

A price carrier method will be applied to compute accurate exchange rates. The computerized exchange will in real time or on an hourly basis at minimum provide the computerized price server with at least the following information through a gateway over the computer network.

These spot exchange rates linear interpolated interest rate curves and theoretical calculated forward exchange rates may be forwarded and used when calculating variation margin and initial margin.

It should be noted that it will also be possible for the clearing operation personnel to manually enter the spot exchange rates and interest rate curves through the Graphical user interface GUI to the clearing system.

Consider a portfolio according to Table 3. All contracts are Spot FX contracts and hence have value date T 2.

It should be noted that since the contracted rates are equal to the fixing rates all positions have market value equal to zero. The margin requirement calculated by OMS II and NOMX CFM will therefore only contain the initial margin.

OMS II will calculate a margin requirement per position. This will be calculated according to Equation 11 and Equation 12.

The total margin requirement converted into EUR with the closing fixing exchange rates will be equal to 84 478 EUR.

Since all payments are for value date T 2 there is no need to perform the present value calculations.

The scanning range parameter is applied in conjunction with converting the net present valued payments into the base currency of the account EUR .

The total margin requirement will be equal to the sum of all net present valued payments in EUR. Margin requirement 0.002 EUR.

The following example is aimed to describe a second embodiment wherein the present invention may be used namely to calculate margins for interest rate swaps. NOMX CFM short for NASDAQ OMX Cash Flow Margin is a margin model designed by NOMX.

Preferably this method is implemented in a computer system such as a computer or server computer comprising a central processor for executing the instructions that are associated with the method steps described in the following example.

In the first step each instrument is broken up into its underlying cash flows and these are inserted into a cash flow table. The columns in this table represent each cash flow s currency and the rows represent each cash flow s value date. Positive and negative cash flows on the same value date and in the same currency and with the same interest rate risk will be netted in this step.

In the second step a net present value NPV of the future cash flows is calculated per currency. The yield curves are stressed when this calculation is performed. This text presents a rolling value method a historical simulation approach and a principal component approach to the yield curve stressing. Each clearing house may however define and use their own method to stress the yield curves.

In the third step each net present valued cash flow is converted into a margin base currency. The spot exchange rates are stressed in this conversion. The window method will be applied to account for correlation between different exchange rates.

It should be noted that if the NPV of the future cash flows are calculated with the unstressed yield curves and converted with the unstressed spot exchange rates then the portfolio s market value is obtained in the margin base currency. However when the NPV are calculated with the stressed yield curves and converted with the stressed spot exchange rates the margin requirement is obtained in the margin base currency.

Consider a bought plain vanilla SEK fixed for floating rate swap for example a two year swap of a fixed interest for floating 3M STIBOR. This could be defined as

Consider a sold USD JPY fixed for floating rate swap for example a ten year swap of a fixed interest in USD for floating JPY 3M LIBOR. This could be defined as

Consider a bought SEK floating for floating rate swap for example a five year swap of SEK 3M LIBOR 20 for 3M STIBOR 25. This could be defined as

 1 000 000 1 2009 05 05 2014 05 05 3M 3M SEK 3M LIBOR 3M STIBOR simple simple 20 25 SEK SEK False 1 .

In order to be able to price and calculate margins on interest rate swaps RIVA must be able to construct yield curves. The NOMX CFM adaptations to RIVA include an OMNET computer transaction in order to send pairs of dates t and interest rates r into RIVA. From this information RIVA will be able to linear interpolate an interest rate curve r t .

A preferred way is that the RIVA computer system collects the relevant swap zero rates from a third party vendor such as Reuters or Bloomberg via computer communication means and uses a linear interpolation of a swap zero curve r t . RIVA can from r t construct a swap forward curve r t . The formula used to construct r t will of course look different depending on the type of interest rates and the discount base. In this text it is assumed that the swap zero rates are simple interest rates and that the discount base is actual 360.

An interest rate swap is an agreement to exchange future cash flows in one or two currencies. An example of the future cash flows of a SEK fixed for floating rate swap is shown in .

It should be noted that the notional amount for CURis given by N FX. Hence when Equation 15 18 are used on the second leg of the swap contract N should be changed to N FX.

In the next step of NOMX CFM method a new row is added to the cash flow table. This row contains the NPV of the future cash flows per currency. It should be noted that if the NPV calculations are performed with each currencies unstressed swap zero curve the market value of the future cash flows is obtained per currency.

Adding a margining aspect to the NPV calculations requires stressing of the yield curves. The Historical Simulation and the Principal Components approach to the yield curve stressing can be applied in this context as well. However the preferred method for stressing the yield curves will be the Rolling Value method. This text presents how the Rolling Value method can be applied on interest rate swaps.

In this method the swap forward curve is shifted in a rolling fashion starting with the cash flow furthest away. The NPV of one currency s future cash flows is given by equation 19 .

p t is the discount function from today to tand it is given by the swap zero rate r t p t t is the discount function from tto tand it is given by the swap forward rate r t t .

A fixed cash flow is always exposed to a shift in the forward curve r t t . However the complete floating cash flow is not exposed to a shift in the forward curve since the same forward curve is used to determine the size of the floating cash flow. A floating cash flow can therefore always be divided into one part that is exposed to shifts in the forward curve and one part that is unaffected by shifts in the forward curve.

CCcan always be divided into one part that is exposed to shifts in the forward curve CC and another part is unaffected by shifts in the forward curve CC. 23 

In the rolling value method the forward curve is stressed with a risk parameter rp depending on the sign of CC. sign 24 

This means that the last cash flow is discounted back to the one before dependent on sign of its exposed part. For the next step the discounted cash flow and the cash flow at that point is added together and dependent on sign of this cash flow s exposed part then discounted back to the cash flow before that. When the last cash flow is reached on time t the discounting must be performed with p t in order to obtain the present value. At this stage the complete CCwill be exposed to a shift in the zero rate r t and hence r t should be stressed depending on sign of CC. sign 25 

When the rolling value method has calculated the NPV of the future cash flows it has at the same time produced the stressed swap forward rates r t t as well as the stressed swap zero rate r t . Equation 13 can now be used to obtain the complete stressed swap zero curve. Hence the rolling value method produces the stressed yield curves in conjunction with performing the NPV calculations as opposed to the other methods that first construct a number of different yield curves and then performs the NPV calculations in order to select the worst curves.

The stressing of the swap yield curves gives a NPV of the future cash flows per currency. In the last step of NOMX CFM method the net present valued cash flows are converted into the margin base currency. The spot exchange rates are stressed in this conversion. The window method will be applied to account for correlation between different exchange rates.

This section contains examples of how method according to an embodiment NOMX CFM method of the present invention would calculate margins for two different swap portfolios.

Consider a portfolio that consists of one sold contract of a two year SEK fixed for floating rate swap.

This implies that every third month a 1 41 fixed rate is received in exchange for the 3 month STIBOR rate. Suppose that the contract is entered on 2009 05 05 and that the swap zero rates r t on this day is as given in Table 12. Equation 13 can be used to produce the SEK swap forward curve r t t .

The rates in Table 13 can be used together with Equation 15 18 in order to create the cash flow table.

The floating cash flow on day tcan be divided in one part that is exposed to and another part that is not exposed to shifts in r t t . The cash flow table can therefore be divided into a non exposed and an exposed part.

The rolling value method starts with the cash flows furthest away i.e. on 2011 05 05. These cash flows are discounted back to the time of the next cash flow i.e. to 2011 02 05 using the forward rate between 2011 02 05 and 2011 05 05 r 2011 02 05 2011 05 05 . The forward rate is stressed with a risk parameter depending on the sign of the exposed part of the cash flow from 2011 05 05. In this example it is supposed that the risk parameter is set to 20 basis points.

CCi.e. the exposed cash flow on 2011 05 05 is equal to SEK 1 003 486 0. Hence the forward curve shall be stressed upward in order to make CCas small as possible.

CCbecomes equal to 1 001 085 0 and hence r 2010 11 05 2011 02 05 shall also be stressed upward. This procedure is repeated until the last cash flow is reached on 2009 08 08.

In order to obtain the NPV of the future cash flows CCmust be discounted back using the swap zero rate r 2009 08 05 . It should be noted that the complete CCis exposed to shifts in r 2009 08 05 and hence it should be shifted based on the sign of CC.

It should be noted that since all stressed forward rates and the first stressed zero rate is obtained Equation 13 can be used in order to construct the stressed swap zero curve. All swap curves are shown in and .

The swap forward curve was stressed upward between 2009 08 05 and 2011 05 08 since CC 0 between these dates. On 2009 08 05 the floating leg did however become exposed to a shift in the swap zero rate and this made change sign. The swap zero rate r 2009 08 08 was therefore stressed downward.

If the NPV of the future cash flow is calculated with the unstressed curves the market value of the swap portfolio is obtained. Table 16 lists the swap portfolio s market value together with the calculated margin.

Consider a portfolio that consists of one bought contract of a five year SEK fixed for floating rate swap versus one sold contract of a two year SEK fixed for floating rate swap.

Suppose that the contracts are entered on 2009 05 05 and that the swap zero rates r t on this day is as given in Table 17. Equation 13 can be used to produce the SEK swap forward curve r t t .

The swap forward curve was stressed downward between 2011 08 05 and 2014 05 05 when there were only cash flows from the five year swap contract in the cash flow table. Between 2009 08 05 and 2011 05 05 the cash flows from the two year swap contract were also exposed to shifts in the swap forward curve and the positive sign of the fixed leg cash flows of the two year swap made the sign of CCchange on 2011 05 05. The forward curve was therefore stressed upward between 2010 02 05 and 2011 05 05. However since the fixed leg of the five year swap contract had a higher traded yield then the fixed leg of the two year swap contract CCgradually decreased and on 2009 11 05 the sign of CCwas changed and the forward curve as well as the zero curve were stressed downward.

Table 19 shows the swap portfolio s market value and the margin produced by the rolling value method as well as by parallel shifting the swap curves upwards and downward.

In some procedural steps of a computerized method for calculating margin requirements implemented on a computer system are illustrated. The computer system can comprise a memory comprising contracts and a processor associated with the memory. In accordance with the method contracts in the memory are first identified in a step . The identified individual contracts are then broken into its respective cash flows in a step . The cash flows of one contract resulting from step can then be netted against cash flows from other contracts in a step . The margin requirements can then be calculated based on the netted cash flows.

In the above description the term comprising does not exclude other elements or steps and a or an does not exclude a plurality.

