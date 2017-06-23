---

title: Central counterparty for data management
abstract: A central counterparty for data management (CCDM) receives data relating to financial transactions, associates the data with metadata to create reference data, stores the reference data and provides the reference data in “push” and “pull” ways. The “push” techniques for providing the data include distributing on a data feed, sending the data to parties known to be relevant to the transaction, and sending the data to parties who have a standing query that is satisfied by the data. The “pull” techniques for providing the data include responding to queries received from a variety of parties. The CCDM generates and distributes unique, unambiguous and universal identifiers (U3id's) and associates the U3id identifiers with the reference data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08055575&OS=08055575&RS=08055575
owner: Financial Intergroup Holdings, Ltd.
number: 08055575
owner_city: New York
owner_country: US
publication_date: 20101118
---
This application is a continuation in part of U.S. patent application Ser. No. 11 544 570 filed Oct. 10 2006 having common inventors herewith which in turn claims priority from U.S. provisional patent application Ser. No. 60 726 984 filed Oct. 14 2005. Each of the Ser. No. 11 544 570 and 60 726 984 applications is hereby incorporated by reference in its entirety.

The present invention relates data processing for the financial industry and more particularly is directed to a centralized repository of static information involved in securities trading with various information distribution capabilities.

Securities trading particularly the post trade activities of clearance and settlement still gives rise to many errors even almost fifty years of increasingly advanced automation.

Another problem is that different departments in a securities firm usually have their own data handling practices and their own databases sometimes referred to as data silos. Accordingly it can be difficult or impossible for a firm to accurately aggregate its own data.

A further problem is that securities firms each maintain their data at their discretion in differing formats and with identifiers of their own choosing so it can be difficult or impossible for a regulatory agency to accurately aggregate data from different firms.

A 2008 survey by TowerGroup asked firms with automated trade processing capability what were the reasons for trades being rejected from automated processing and obtained the following results 

In the US alone in just one payment and settlement facility Depository Trust and Clearing Corporation DTCC nearly 7.5 trillion of traded value is associated with trade matching on any one day. There are nearly 100 such facilities globally. Although DTCC is by far the largest these error rates are significant to the values at risk at such facilities globally.

Thus there is a need for improved techniques for processing financial information in the securities industry.

In accordance with an aspect of this invention there is provided a method of distributing financial reference data comprising receiving by a computer external data from a data source associating by the computer the external data with metadata to generate reference data storing by the computer the reference data transmitting by the computer the reference data on a data feed to a data consumer comparing by the computer the reference data with a standing query and when the reference data satisfies the standing query sending by the computer the reference data to an owner of the standing query.

In accordance with another aspect of this invention there is provided a method of using financial reference data comprising receiving by a first computer the financial reference data from a second computer and appending by the first computer the financial reference data to a trading order wherein the financial reference data results from receiving at the second computer external data from a data source and associating at the second computer the external data with metadata to generate the reference data.

In accordance with a further aspect of this invention there is provided an apparatus for distributing financial reference data comprising a first communication interface for receiving external data from a data source a processor for associating the external data with metadata to generate reference data a data storage for storing the reference data a second communication interface for transmitting the reference data on a data feed to a data consumer wherein the processor is also for comparing the reference data with a standing query and when the reference data satisfies the standing query sending the reference data to an owner of the standing query.

It is not intended that the invention be summarized here in its entirety. Rather further features aspects and advantages of the invention are set forth in or are apparent from the following description and drawings.

The present invention is a central counterparty for data management CCDM that receives data relating to financial transactions associates the data with metadata to generate reference data and provides the reference data in push and pull ways. The push techniques for providing the data include distributing on a data feed sending the data to parties known to be relevant to the transaction and sending the data to parties who have a standing query that is satisfied by the data. The pull techniques for providing the data include responding to queries received from a variety of parties.

The metadata may be received from the source of the data or added by the CCDM. The metadata may be stored explicitly such as by an identification field or implicitly such as in a particular pre defined field of a database.

Another important function of the CCDM is to generate unique unambiguous and universal identifiers each referred to as a U3id to associate the U3id identifiers with reference data and to distribute the U3id identifiers to public commercial and government entities.

Numbering agency provides an identifying number for a security. Standard Poor s is an instance of numbering agency . A CUSIP is an instance of an identifying number.

The acronym CUSIP historically refers to the Committee on Uniform Security Identification Procedures and is a 9 character alphanumeric code that identifies any North American security for the purposes of facilitating clearing and settlement of trades. The CUSIP distribution system is owned by the American Bankers Association under its status as a National Numbering Agency such status given by the International Standards Organization ISO and is operated by Standard Poor s. The CUSIP Service Bureau acts as the National Numbering Association NNA for North America and the CUSIP serves as the National Securities Identification Number for products issued from both the United States and Canada. The first six characters are known as the base or CUSIP 6 and uniquely identify the issuer. Issuer codes are assigned alphabetically from a series that includes deliberate built in gaps for future expansion. The 7th and 8th digit identify the exact issue. The 9th digit is an automatically generated checksum some clearing bodies ignore or truncate the last digit . To calculate the check digit every second digit is multiplied by two. Letters are converted to numbers based on their ordinal position in the alphabet. The last three characters of the issuer code can be letters in order to provide more room for expansion.

Public data communication network is a packet switched communication network incorporating routers trunk lines access lines and so on. The Internet is an instance of network .

Registrar bank provides share registry services for issuers of publicly traded securities such as Newco . Generally share registry services include keeping track of how many shares the company has issued who owns the shares ensuring that the total shares at stock depository equal the total shares issued by Newco and serving as the transfer agent for owners of Newco shares keeping books and records on their behalf.

Investment bank represents a company that issues securities and takes care of the administrative details of issuing the securities and also sells places the securities on behalf of the company. Typically investment bank creates a draft Offering Memorandum in compliance with securities offering laws called a red herring and distributes the red herring to prospective share purchasers possibly via other investment banks and often in conjunction with an in person presentation of the company to prospective purchasers called a road show . Based on response to the red herring investment bank determines the price for the securities and then files the actual Offering Memorandum with the initial price to enable the start of public trading.

Securities regulator is a government entity tasked with monitoring and regulating the financial industry.

Investment manager is an individual or firm that manages an investment fund on behalf of the fund owner such as an individual or a group of individuals a mutual fund a pension fund deciding when to buy and sell securities and often deciding which securities to buy and sell which trading platform to use and which trading firm to use.

Financial industry post trade data processor provides to investment manager custodian bank trading firms and and stock depository automated trade life cycle events including notice of execution allocation confirmation affirmation settlement notification enrichment of trades with standing settlement instructions operational analytics and counterparty risk management between trade counterparties. Omgeo is an instance of financial industry post trade data processor .

Trading company is a marketplace for securities trading such as NYSE Euronext. The actual trading occurs on trading platform operated by trading company . NYSE Equities NYSE Arca Equities Euronext Equities and ArcaEdge are instances of trading platform .

Trading firms and are members of trading company and provide order entry execution and post trade services to their customers and may also have proprietary accounts that they trade on their own behalf.

Stock depository provides clearing and settlement efficiencies by immobilizing securities and making book entry changes to ownership of the securities. Stock depository serves as the transfer agent for the financial industry keeping books on behalf of trading firms. Depository Trust Corporation DTC is an instance of stock depository .

Clearing corporation provides clearing settlement risk management central counterparty services and a guarantee of completion for certain transactions for virtually all broker to broker trades involving equities nets trades and payments among its participants reducing the value of securities and payments that need to be exchanged each day. Clearing corporation generally clears and settles trades on a T 3 basis. National Securities Clearing Corporation NSCC is an instance of clearing corporation . DTC provides securities movements for NSCC s net settlements. DTC and NSCC are owned by DTCC.

On trade date T the clearance and settlement cycle begins. Trade details are electronically transmitted to clearing corporation for processing. For equity transactions while 99.9 are sent as locked in trades which means that the marketplace has already compared them at the time of execution confirming all details includes share security quantity and price the potential for errors introduced after this lock in is still significant. Additional processes described as clearance and settlement must follow to actually distribute securities to new owners from previous ones and make payment between these same parties and or their agents. Clearing corporation sends to participants automated reports showing trade details for transactions that have entered clearance and settlement processing.

Clearing corporation guarantees settlement for cleared trades. The guarantee generally begins at midnight between T 1 and T 2. At this point clearing corporation steps into the middle of a trade via a legal process called novation and assumes the role of central counterparty taking on the buyer s credit risk and the seller s delivery risk. This guarantee eliminates uncertainty for market participants and inspires public confidence.

Two days after trade date T 2 clearing corporation issues summaries of all compared trades including information on the net positions of each security due or owed for settlement.

Three days after trade date T 3 is settlement day when securities are delivered to buyers and money is paid to sellers. Trading firms instruct their settling banks to send or receive funds through the Federal Reserve System to from depository corporation as the agent for clearing corporation . Securities generally do not change hands physically.

At step Newco hires investment bank to serve as its representative for an initial public offering of shares in Newco .

At step investment bank requests a symbol for Newco from trading company to be used to designate shares of Newco on trading platform .

At step numbering agency assigns nbrXYZ as the symbol identifier and sends this to all parties that are subscribers to the new identifier update service of numbering agency .

At step firm a subscriber to the new identifier update service of numbering agency receives the information associating Newco XYZ and nbrXYZ.

At step registrar bank receives the newly obtained symbol and symbol identifier and forwards this information to depository .

At step investment bank presents the new security to potential buyers at various meetings road show assesses interest and advises that the initial offering price will be 12 per share. Firm gets the identifier via an automated feed from numbering agency . Firm sees the identifier in the red herring and manually enters the identifier into its system.

At step firm commits to buy 3 000 000 shares at the initial price. Typically firm combines orders for its own proprietary trading account with customer orders to arrive at its total commitment.

At step investment bank notifies registrar bank that when trading commences firm will own 3 000 000 shares and firm will own 2 000 000 shares.

On the actual initial public offering date not shown as soon as trading starts firms and are recognized as the share owners. Assuming there are no other buyers no sale activity occurs and the total share offering was 10 000 000 shares at the end of the day each of registrar bank and depository have recorded share ownership as follows 

Let it be assumed that some time after the initial public offering firm decides to sell 100 shares of XYZ at the market price for its own account and firm decides to buy 100 shares of XYZ for its own account.

At step trader A at firm creates a sell order for 100 shares of XYZ at the market price and sends it to trading platform .

At step trading platform receives the sell order validates its terms and stores the sell order in its trading book that is its database of orders waited to be executed.

At step trader B at firm creates a buy order for 100 shares of XYZ at the market price and sends it to trading platform .

At step trading platform receives the buy order validates its terms and searches for any possible matches prior to storing the order in its trading book.

At step trading platform finds the sell order from trader A and matches it with the buy order from trader B thereby creating an executed trade.

At step trading platform sends trade reports also known as execution reports to the parties involved in the trade and to clearing corporation . The trade report to trader A is as follows 

At step firm matches the settlement notice with the execution report that it bought 100 shares of XYZ.

At step clearing corporation receives the affirm from firm . The trade is now fully confirmed. Clearing corporation novates itself into the trade creating a first legal obligation to buy 100 shares of XYZ from firm and a second legal obligation to sell 100 shares of XYZ to firm and guarantees to each of firms and that its respective obligation will settle on T 3. Then clearing corporation aggregates all activity for XYZ for firm to create a net position for that day s activity and aggregates all activity for firm to create a net position for that day s activity. For this example we assume that the only trade that occurred during the day was the sale of 100 shares of XYZ. Clearance is now complete.

At step clearing corporation sends share transfer instructions to depository to transfer 100 shares of XYZ from the account of firm to firm .

At step depository transfers the shares. Depository has recorded share ownership as follows assuming that only this one trade of 100 shares of XYZ occurred since the security was issued.

At step clearing corporation transfers cash in its internal cash accounts from the account for firm to the account for firm . In some embodiments instead of using internal cash accounts clearing corporation sends instructions to the banks associated with firms and or if firms and can interact directly with the federal funds transfer system then to them.

At step firm matches the share transfer notice with the execution report and concludes that the trade is fully and properly settled.

At step firm matches the share transfer notice with the execution report and concludes that the trade is fully and properly settled.

It will be seen that due to the frequent matching of information regarding the progress of the trade the errors are discovered and are likely to be corrected. However there is still a large cost for the manual processing required for errors. Furthermore if the manual processing does not finish by T 3 the firm will have to borrow cash or stock to ensure settlement which is costly and then may have to be reversed when error processing concludes.

It will be appreciated that other trading data errors also occur with similar consequences the cost for manual error processing and additional costs if the manual error processing does not complete by T 3.

At step clearing corporation sends a settlement notice to firm showing that firm bought 100 shares of Gemco symbol JMO.

At step firm tries to match the settlement notice that it bought 100 shares of JMO with the execution report that it bought 100 shares of XYZ but since they do not match the settlement notice remains unmatched and is flagged in an automatically produced error report. A clerk at firm or an automated error handling system at firm suspects that the settlement notice should match the execution report perhaps because the identifier nbrXYZ is on both the notice and report or perhaps because the same share quantity is on both the notice and report or perhaps because the same execution time is on both the notice and report. Generally a clerk at firm will call a clerk at clearing corporation and hopefully notice that clearing corporation has the wrong company name for the identifier nbrXYZ.

At step clearing corporation sends a settlement notice to firm showing that firm sold 100 shares of Gemco symbol JMO.

At step firm is unable to match the settlement notice that it sold 100 shares of JMO with the execution report that it sold 100 shares of XYZ. Similar processing occurs in firm as occurred in firm at step .

At step clearing corporation receives the correction notice from firm . A clerk at clearing corporation decides that the trade has been cleared and ensures that the error in the database is corrected.

In general a financial enterprise may need to access sources of corporate event information globally from stock exchanges central depositories commercial data vendors issuer prospectuses and press releases and newspapers. This is a massive amount of information that needs to be collated validated captured in codes and then put into a structured syntax that can be processed by a software application. For example there are nearly 100 different types of corporate actions and different laws dictate how each company must report this information. As business laws across different countries are not harmonized the rights of shareholders pursuant to an event are not the same across different markets thus making the communication of corporate events hard to standardize globally. Additionally this information is required for adjustments to indexes futures options and derivative products that have securities underlying these instruments. Also notification of these events culled from these numerous sources gets passed through a long chain from issuer and registrar and on through sub custodians global custodians the Depository Trust Company Clearing Corp. DTCC here in the US other foreign central depositories vendors broker dealers and investment managers.

Corporate event information arrives at an entity in varied formats from different data vendors is sometimes confusing to understand and at other times is incorrect when a particular data vendor made a mistake in converting manual data such as press releases to digital data. Because of this each entity typically obtains information from multiple but different data vendors and compares the obtained information to discover discrepancies thereby preventing reliance on incorrect information. These discrepancies then have to be followed up on usually through manual intervention back to the originating source and repaired.

At step clearing corporation sends share transfer instructions to depository to transfer 100 shares of XYZ from the account of firm to firm . Because of the dividend this is an error clearing corporation should have instructed depository to transfer 200 shares of XYZ.

At step firm cannot match the share transfer notice for 100 shares with the execution report as updated to reflect that it bought 200 shares. Accordingly the share transfer notice is put on an automatically generated error report. Probably the execution report also appears on an automatically generated error report as being unmatched. A clerk at firm hopefully realizes that the discrepancy in the number of shares is due to XYZ s dividend and calls depository and clearing corporation to correct the error. Until the error is corrected the clerk in firm notifies trader B that the trade has not cleared and trader B cannot trade the missing shares of XYZ which could be highly disadvantageous in a fast moving market.

Let it be assumed that Firm C not shown operates mutual fund AA BB and CC and has engaged investment manager to trade for its mutual funds.

Firm C uses custodian bank as custodian for its mutual funds. Custodian bank outsources some of its data processing functions to financial industry post trade data processor .

Investment manager uses firm for its trades during set up of the trading account for investment manager firm was instructed as to the relationships of the parties.

Some time after the initial public offering of XYZ investment manager decides to sell 500 shares of XYZ for mutual fund AA sell 200 shares of XYZ for mutual fund BB and sell 500 shares of XYZ for mutual fund CC that is to sell a total of 1000 shares of XYZ.

Coincidentally at the same time trader B of firm decides to buy 1000 shares of XYZ for the proprietary trading account of firm .

At step firm sends an affirm notice to clearing corporation accepting the settled trade and instructing clearing corporation that financial industry post trade data processor will provide the account locations to be debited by depository .

At step clearing corporation receives the affirm from firm including the instruction to look to financial industry post trade data processor for share locations.

At step which ideally occurs on T but could occur as late as the morning of T 3 investment manager sends an allocate message to custodian bank and financial industry post trade data processor explaining how to allocate its 1000 share trade among mutual funds AA BB and CC. While larger investment managers have fully computerized systems smaller investment managers such as single person firms still use manual techniques for sending messages such as sending a handwritten fax.

At step custodian bank receives the allocate message and at step acknowledges receipt of the allocate message to investment manager .

At step financial industry post trade data processor receives the allocate message from investment manager .

In some embodiments investment manager communicates only with financial industry post trade data processor which in turn provides daily position update reports to custodian bank .

At step clearing corporation sends a share source request to financial industry post trade data processor .

At step financial industry post trade data processor receives the share source request and at step provides the share source that is the account for firm C to clearing corporation .

At step clearing corporation receives the share source instructions. The trade is now fully confirmed.

If investment manager was slow about providing its allocate message then although step the request for share source from clearing corporation occurred on T financial industry post trade data processor would be unable to provide the share source at step until as late as the morning of T 3.

At step clearing corporation sends share transfer instructions to depository to transfer 1000 shares of XYZ from the account of firm C to firm .

At step depository sends a share transfer notice to each of financial industry post trade data processor and firm .

At step financial industry post trade data processor matches the share transfer notice with the allocation message and concludes that the trade is fully and properly settled.

At step financial industry post trade data processor updates its records for firm C to allocate the cleared shares to mutual funds AA BB and CC in accordance with the allocate message from investment manager .

As in the proprietary account trading examples discussed above it will be seen that due to the frequent matching of information regarding the progress of the trade the errors are discovered and are likely to be corrected. However there is still a large cost for the manual processing required for errors. Furthermore if the manual processing does not finish by T 3 a firm trading on behalf of a customer will have to borrow cash or stock to ensure settlement which is costly and then may have to be reversed when error processing concludes.

It will be appreciated that other trading data errors also occur with similar consequences the cost for manual error processing and additional costs if the manual error processing does not complete by T 3. Furthermore the delay in entering into a trade and then waiting three days or more for the finality of settlement and payment has inherent and systemic risk built into the entire end to end process. Significant risk of default is associated with a firm or client involved in the transaction declaring bankruptcy during the transactions life cycle. Also cash flows from other markets that are surrogates for stocks such as options or futures have shorter trade to settlement payment life cycles even certain markets such as government securities markets settle in real time while available earlier cannot be offset from stock markets cash flows until three days forward. This causes significant overnight borrowing to synchronize these cash flows with the potential of bank defaults.

In this case the error is that investment manager has the wrong custodian bank associated with mutual funds AA BB and CC. This can easily occur if firm C changes its custodian bank from another bank to custodian bank but forgot to tell its outside investment manager . Or firm C could send a notice of change of custodian bank to investment manager who could not get around to updating its records.

At step which ideally occurs on T but could occur as late as the morning of T 3 investment manager sends an allocate message to another custodian bank not shown in namely the old custodian bank and to financial industry post trade data processor explaining how to allocate its 1000 share trade among mutual funds AA BB and CC.

At step the other custodian bank receives the allocate message and at step sends a reject message back to investment manager .

At step investment manager receives the reject from the other custodian bank. Investment manager now has to figure out why the reject occurred. For small investment managers this could take a few days as they may not have dedicated clerical staff that is the investment manager may do his or her own error handling and if the investment manager is on vacation while the error occurs they will not get around to dealing with the error in the normal trade processing cycle. In this case let it be assumed that investment manager promptly calls firm C to confirm the identity of the custodian bank and learns that the custodian bank has changed to custodian bank .

At step investment manager sends a corrected allocate message to custodian bank and to financial industry post trade data processor .

At step custodian bank receives the allocate message and at step sends an acknowledgement message to investment manager .

Other prior art error can occur that are not even noticed and therefore do not get corrected. Actions depending on the uncorrected data will thus be based on erroneous information and so the actions taken may be wrong.

Two examples of unnoticed and uncorrected errors will now be discussed. The first relates to intra firm data aggregation that is used for risk management. The second relates to data aggregation used for regulatory awareness of the financial industry.

In this case let it be assumed that a firm trading for its own account such as a hedge fund has a risk management system with two position limits for security indicating how big a position can be taken by an individual trader in the security and how much overall exposure the firm will tolerate for the security.

As sometimes occurs different trading marketplaces assign the same symbol to different securities since there is no overall coordination of symbol assignment. For instance the symbol NQL on the Toronto Stock Exchange trading platform corresponds to the security NQL Energy Services Inc. Class A stock while the symbol NQL on the American Stock Exchange trading platform owned by NYSE Euronext corresponds to TIERS Principal Protected Trust Certificate Series NASDAQ 2002 6 security.

The firm has risk management system with database showing the two position limits for each security and has correctly represented that NQL corresponds to two different securities and has different position limits for overall firm exposure for these two securities.

The trades of traders and are in databases and respectively. These traders each have one position in NQL but have not specified which NQL their position is for.

In this example the positions of traders and are consistent with the individual trader position limits for both NQL so no alarms are triggered.

If risk management system is programmed to aggregate unspecified NQL positions as NQL TSE then no alarms will be triggered as the sum of the positions of traders is less than the overall firm limit for NQL TSE.

However if traders and each have positions in NQL ASE then the firm s overall exposure has been exceeded and an alarm should be triggered in risk management system . But no alarm occurs. Accordingly the firm s management believes their risk is properly contained whereas in reality their risk is more than they want. However no one in the entire firm is aware of the problem and all systems appear to be operating properly and all traders believe their exposure is as desired by the firm s management.

Firm has departments A A and A that are respectively supplied with data from data vendors DV DV and DV. For example department A might be a proprietary trading securities group and appreciates the stock charting features in the data feed from data vendor DV department A might be retail trading and gets only bare bones market data from data vendor DV while department A might be another proprietary trading group focused on derivatives that uses the underlying security market data from data vendor DV along with its derivative market data.

Firm has departments B B and B that are respectively supplied with data from data vendors DV DV and DV.

Securities regulator requires daily position reports from firms and and then uses market data from data vendor DV to convert the positions to cash exposures which are compared against the reserve capital for the firm to understand its leverage.

Each trading platform reports a closing price for its daily trading. The closing price is usually the same as the price at which the last trade occurred. However each trading platform can define its closing price according to its own rules for example as the average of the price at which the last three trades of the day occurred.

The closing price is also referred to as a last sale price or a valuation price . The closing price is very important as most investors perform daily mark to market valuations of their investments using the closing price for their securities.

There are hundreds of trading platforms in the world nearly 80 trading platforms are in the United States. Various data vendors receive the closing prices from some or all of the trading platforms and in turn generate and distribute at the end of each trading day a closing price data feed. However the various data vendors do not always report the same closing price for a particular security at a particular trading platform for myriad reasons including a the vendor has installed a new software interface that does not properly handle closing prices b the vendor failed to get a price adjustment notice from a trading platform c the vendor s internal cut off time for assembling data for its closing price data feed was earlier than the time that the trading platform issued an adjusted closing price and so the vendor will report the adjustment on the next day and so on.

Then due to corrections made at trading platform at step trading platform reports a first corrected closing price as part of its market data information.

Due to further corrections made at trading platform at step trading platform reports a second corrected closing price as part of its market data information.

For instance Notice 1 averaged the last three prices of the day given that the last price was of a disputed trade price far from the previous last trade. The last price was left standing but averaged in and recalculated in a new valuation price. Notice 2 changed the valuation price a second time as it was usual for floor governors to review immediate closing price judgments this time removing the disputed last trade thus leaving the previous trade as the last trade and defining it as the valuation price.

At step data vendor DV receives the original valuation price and distributes it to departments A of firm and B of firm .

At step data vendor DV receives the notice 1 price and distributes it to departments A of firm and B of firm .

At step data vendor DV receives the notice 2 valuation price and distributes it to departments A of firm and B of firm .

Here the error is that the data vendors did not all pick up all of the corrections. Accordingly their closing prices differ.

At steps and departments A A and A receive the respectively different closing prices. At step firm computes its overall XYZ position and reports it to regulator . At step regulator receives the position report from firm .

At steps and departments B B and B receive the respectively different closing prices. At step firm computes its overall XYZ position and reports it to regulator . At step regulator receives the position report from firm .

In a further step not shown regulator uses the data from data vendor DV to calculate overall positions based on the reports from firms and . At best the closing price from DV matches one of the closing prices from one of the vendors DV DV DV and is the correct notice 2 price. However data vendor DV could also have the wrong price.

Of concern is that regulator does not know that the data from the various firms are internally incommensurate and further does not suspect that its selected data vendor DV may compound errors.

A financial transaction becomes associated with additional reference data as it moves through its life cycle. For instance a trader may decide to buy 100 XYZ at 21.54 then the trader s order entry system associates XYZ with Newco common stock and associates 21.54 with US dollars . Here the full name of the security is an instance of reference data and the currency is another instance of reference data. The order entry system then selects trading platform TP because of an order flow rebate arrangement that the trading firm has negotiated with that trading platform and associates sent to trading platform TP with the order. At trading platform TP the buy order is matched with a sell order and the trading platform associates trade date time information sale price information and counterparty information with the transaction. Additional reference data may be appended to the transaction during clearance and settlement.

Financial transactions which increasingly are exclusively information based are represented as a series of data elements that collectively represent their unique unalterable attributes referred to as static data their occasional adjustments as in corporate events or changes of corporate ownership and their variable transaction components such as traded date quantity and price. The unalterable characteristics and occasional adjustments collectively termed reference data uniquely identifies the product security number and market its unique structure financial attributes its manufacturer counterparty dealer or exchange its delivery point delivery or settlement instructions its valuation price closing or settlement price its currency and its expected delivery time.

So called high frequency traders locate their computers physically near to the computers of trading platforms to minimize transmission delays. The trading platforms typically charge extra for the so called low latency data provided to the co located computers of the traders. The low latency data is not well suited for the CCDM. However the trading platforms provide the same data at normal latency and the normal latency version of the trading data is well suited for the CCDM.

Reference data uniquely identifies a financial product security number symbol market etc. its unique type terms and conditions asset class maturity date conversion rate etc. its manufacturer or supply chain participant counterparty reference entity dealer institution exchange etc. its delivery point delivery settlement instructions and location its delivery or inventory price closing or settlement price and its currency. Analogous to specifications for manufactured products reference data also defines the products changing specifications periodic or event driven corporate actions and seasonal incentives or promotions dividends capital distributions and interest payments 

Conventionally reference data is attached incrementally at various stages in the life cycle of a financial transaction either by the selection or input of such information by a human being by looking up information on a computer file if it is being entered for the first time or through computerized access to previously prepared directories and or financial transactions as when one had previously bought a stock and then prepares to sell it. Reference data occurs beginning in pre trade assembly through to final settlement and payment.

The current practice of acquiring cleansing and storing reference data is to disassemble by manual means the elemental details present in a prospectus offering memorandum financial event announcement incorporation or business organizational documents ISDA master agreement and other such paper documents. For example for a financial event announcement i.e. a tender offer a merger a dividend announcement in this instance sent as a press release or transmitted as text as shown in Table 1 the text must be parsed manually and placed in formatted context for input to a computer.

This process is performed by a myriad of commercial data vendors as well as directly by financial institutions. In many instances multiple interpretations of what is assumed to be the same data is created. These multiple sources are bought by financial institutions from these vendors often in proprietary formats and inconsistent identification and matched within a financial institution to determine discrepancies in order to create a golden copy. Because there are multiple identifiers for the same security or business an extensive mapping exercise is required within each financial institution or through commercial mapping services to conform a single representation of the elements of each security or business or financial event relating to either.

Reference prices for some non exchange traded instruments are aggregated and distributed by their dealer associations others have no central mechanism for aggregation and are either left to individual firms calling around to get dealers prices or left to entrepreneurs to build an aggregation and distribution service. Still other financial instruments which either trade infrequently or are not expected to trade at all are priced through formula. Municipal bonds and over the counter derivatives are examples requiring such reference data as credit ratings historical prices calendar data etc. as inputs to these calculations.

Conventionally reference data can be accessed via each business s processing application so as to incorporate the required reference data according to the specific business rules for the transaction to be represented as a stock trade bond trade futures trade swap credit derivative etc. Sometimes the business application accesses its own data base of reference data each financial institution usually having multiples of reference data bases. Sometimes there is a central store of reference data within the organization sometimes an external store as when such information is outsourced.

The problem simply stated is that each financial institution each separate business unit within a financial institutions and or each supply chain intermediary has independently sourced stored and applied reference data to their own copy s of their individual or master inventory and counterparty data bases. When this is applied to the variable components of a financial transaction i.e. transaction specific data such as quantity and transaction price and an attempt made to match identically the details sent by the counterparties and supply chain participants in order to accept and pay for the transaction significant failures in matching occurs as explained above.

Conventionally various parties attempted to collect and or rationalize the reference data after it was in use.

In contrast CCDM is either the source of reference data or receives the reference data immediately after its creation. In other words prior art solutions for reference data employed a back end approach whereas CCDM employs a front end approach.

In some embodiments CCDM reformats data received from external parties into an internal storage format in which the data is associated with metadata. The reformatting process is sometimes referred to as normalizing the data. Metadata is informational data about content data that is informational data indicating what the content data means.

Extensible markup language XML schemes are well known for financial data including Extensible Business Reporting Language XBRL Extensible Financial Reporting Markup Language XFRML Financial Information Exchange Markup Language FIXML Financial Products Derivatives Markup Language fpML Fixed Income Markup Language FinXML Investment Research Markup Language IRML Mortgage Bankers Association of America MISMO XML Market Data Definition Language MDDL Open Financial Exchange OFX Mortgage Industry Architecture MIXA Society for Worldwide International Financial Transactions Markup Language SWIFTML .

Many schemes exist for describing financial data. For example the date Sep. 20 2001 is represented in different schemes as follows 

CCDM comprises at least one general purpose computer including memory storage data transmission displays and other peripherals so as to operate as described herein. The equipment used for CCDM is conventional and various forms and configurations thereof are well known to those of ordinary skill in the art.

CCDM is adapted to receive financial transaction data store it possibly reformat it and retransmit it as part of its data feed. Generally CCDM is concerned with commoditized data rather than the proprietary high value analytic data sold by various data vendors. Dynamic data source and static data source each provide data to CCDM . In turn CCDM provides dynamic and or static data feed s to data consumers . Note that sources of one type of data may be consumers of another type of data.

Fix Protocol Ltd created the Financial Information Exchange FIX protocol to standardize the communication of pre trade and trade information. Since 1995 it has allowed counterparties and supply chain participants in capital market transactions to communicate electronically such information as indications of trading interest placement of orders receipt of executions and the allocation and confirmation of trades for delivery and payment.

In some embodiments CCDM generates its data feeds with incorporated metadata such as a markup language.

Historically data feeds have used the position of information to indicate its meaning this opens the door to errors. It is better practice to associate metadata with the data greatly reducing the chance of errors.

CCDM is further adapted to receive inquiries and respond thereto. Inquiries are either standing inquiries or one time inquiries. A standing inquiry persists until it is cancelled and usually results in multiple responses over time from CCDM . A one time inquiry results in one response from CCDM . Inquirer submits an inquiry to CCDM and CCDM responds thereto.

CCDM is also adapted to receive requests for error reimbursement for errors relating to the data distributed by CCDM . As described below the error activity is used in an internal risk management process to adjust the reserve capital for CCDM . Error claimant submits an error reimbursement request and CCDM responds thereto.

CCDM includes high speed data bus enabling its internal modules to communicate with each other at high speed. In some cases CCDM has computers located in different cities and high speed data bus may be configured to bridge between the computers located in different cities.

CCDM includes rules data audit data loss history data static data dynamic data and standing queries . The data maintained by CCDM is sometimes referred to as its data pool. The data for CCDM is discussed further below.

Loss history data includes problems for which CCDM provided error reimbursement and problems for which CCDM did not provide error reimbursement. Loss history data includes the occurrence frequency reason and resolution of mismatched pre trade and post trade financial transactions.

Vendor Data Pools are of special interest as they can be a source of inconsistent and incorrect information as the information may be obtained from multiple sources each different from the other. Such errors can occur for valuation prices in financial event data and in business entities and their legal hierarchies. This can lead to different valuations for the same financial instrument different payments for an asset that has accrued a dividend and in different reporting aggregations of a business credit limit or risk exposure by using erroneous legal entity identities or associations.

CCDM acquires inconsistent perhaps incorrect reference data from such Vendor Data Pools from governments and regulators from financial institutions i.e. exchanges clearing houses settlement facilities securities depositories electronic dealers electronic trading networks national numbering associations accredited trade associations etc. and from regulated electronic distributors of reference and market data such as Securities Information Providers US and Multilateral Trading Facilities EC and using its data rules eliminates or reduces the inconsistency in the data prior to storing it in its own data pool.

In particular CCDM automatically associates metadata with data received from data vendors. The metadata enables disparate data to be understood as disparate and further enables commensurate data to be understood as commensurate. For instance a price could appear different from different data vendors but once currency conversion is considered the price becomes commensurate across data vendors.

CCDM automatically stores the reference data matched with a U3id reducing opportunities for error. For instance CCDM generates a U3id for each corporate action and maintains in dynamic data a history of corporate actions that can be indexed using their U3id.

CCDM matches reference data contained within pre trade configured financial transactions received from broker dealers asset managers and custodians to the aggregated plurality of reference data stored on data storage devices. The matching comprises constructing an index from the U3id reference data contained within the pre trade configured financial transactions and accessing the previously stored reference data and matching the retrieved reference data to the reference data contained within the pre trade configured financial transactions.

Where the U3id data does not match no retrieval will be available and CCDM stores an indicator that no match has occurred. Where no match has occurred the computer processing modules will attempt to match each component of the plurality of reference data stored on the computer storage devices based upon a predetermined sequence of the individual reference data elements contained in the pre trade configured financial transactions i.e. financial instrument ID Symbol market et al 

Where matches do occur a tag number will be calculated and logged within the CCDM Data Pool and the validated matched pre trade configured transactions with all requested and validated reference data will be routed to the originator of the transaction.

CCDM distributes a notice of mismatched pre trade configured financial transactions back to broker dealers asset managers custodians and others in accordance with rules provided by such entities.

CCDM enables broker dealers asset managers custodians and others to communicate with computer storage devices a sub set of reference data now contained within post trade financial transactions

Message profiles standing queries are created by broker dealers asset managers custodians and other users and commercial redistributors of reference data for determining general or specific content as contained within post trade financial transactions to be matched to computer storage devices storing a plurality of reference data.

Where U3id matches do occur CCDM calculates a tag number and logs it and sends the validated matched post trade transaction with all requested and validated reference data to the originator of the transaction.

Where the data does not match no retrieval will be available and CCDM stores an indicator that no match has occurred. Where no match has occurred CCDM attempts to match each component of the plurality of reference data stored on the computer storage devices based upon a predetermined sequence of the individual reference data elements contained in the post trade financial transactions i.e. financial instrument ID client business entity ID supply chain ID clearing location ID settlement depot ID etc.

CCDM is usually embodied in a multi processor configuration where each processor is a general purpose computer configured to perform selected operations. CCDM includes one or more receive processors one or more analysis processors and one or more transmit processors each configured with suitable memory storage and communications facilities to operate as described herein.

Receive processor is adapted to receive data store the received data and notify transmit processor that new data is available to be transmitted. External data is provided to receive processor via firewall . External data may be provided to firewall via dedicated communication facilities as is appropriate for high density data sources such as trading platform and data vendor which are instances of dynamic data source and static data source shown in . Firewall may also receive external data from public communications network such as the Internet and from virtual private networks operating via public communications network .

Public communications network includes wire line and wireless communications facilities supports data transmission in clear text or encrypted form and includes circuit switched and packet switched communication channels.

Transmit processor is adapted to receive notifications from receive processor that data is available for transmission and to transmit the data to data consumers . The data may be included in the notification of its availability may be sent directly from receive processor or may be retrieved from a database coupled to high speed data bus . Transmission occurs via firewall . Transmission may be via dedicated communication facilities as is appropriate for a data feed a high density stream of data provided to entity such as a data vendor a trading platform or a large trading firm. Transmission may alternatively be by public communications network .

Analysis processor is adapted to receive queries and to respond thereto generally guided by data rules . Analysis processor is coupled to firewall that is in turn coupled to website server that is coupled to public communications network .

Website server provides one or more web sites accessible through public communications network . One portion of website server requires a password and sometimes additional authentication to access its pages. Another portion of website server responds to public anonymous inquiries. Generally website server has a predefined set of web pages that it serves to visitors and is capable of dynamically creating web pages as needed during a dialog with visitors. Some web pages provide dynamic data in a streaming format. Website server operates according to a suitable protocol such as hypertext transfer protocol.

Although only one instance of each of firewalls is shown it will be understood that many instances may be provided as is appropriate for the data volume. Each of firewalls includes at least one communication interface and at least one processor and further includes suitable memory and storage for operating as described herein.

The following external entities are shown as coupled to public communication network and thus are able to communicate with CCDM 

At step a data source such as data vendor or trading platform provides data to CCDM . An instance of data is a securities trade execution report including identification of the parties to the trade.

At step receive processor validates the data that is checks that its values are within reasonable bounds and that the source of the data is authorized to submit this type of data to CCDM . When receive processor is unable to validate the data it is stored for later exception reporting and analysis not shown .

Ideally the data source provides the data in the internal format used by CCDM that is with metadata tags. CCDM publishes an application programming interface API to assist data sources in providing data in the desired format. However some data sources will simply provide data in their own internal format. Generally CCDM uses a filter customized for each external data source that receives such data and automatically reformats it. However the filter is not able to deal with all externally provided data and when it cannot properly process the data it writes an exception report for manual handling of the data.

At step receive processor checks whether this data is of a type suitable for one of the data feeds provided by CCDM . For instance data from a trading platform is usually intended for a data feed provided by CCDM whereas data from a data vendor relating to say a derivative security associated with a data feed security is not intended for a data feed provided by CCDM rather it is intended to be stored and used in responding to one time queries. If the data is suitable for a CCDM data feed processing continues at step otherwise processing continues at step .

At step receive processor sends a notification message to transmit processor that data is available for transmission.

At step transmit processor format the data for one or more data feeds and sends the data to entities that have subscribed to the data feed. For instance one data feed may be for trades from a predefined set of trading platforms another data feed may be for quotes relating to certain securities and so on.

At step transmit processor checks its data rules to see if there are any interested parties and if so at step sends the data to them. For example it is assumed that a company is interested in all data related to itself. One instance of a standing rule is send data about Newco to Newco which may be overridden by Newco. Another instance of a data rule is when an investment firm associated with an investment manager changes its custodian bank send a notice of the change to the investment manager . A purpose of data rules is to automate a portion of back office administrative functions.

At step transmit processor checks whether there are any standing queries. Generally a standing query is submitted via website server using a structured interface such as drop down menus checking data for reasonable values and so on. In some cases standing queries are submitted by administrator . In other cases analysis processor generates standing queries according to rules data . If so at step transmit processor formats the new data to be responsive to the standing query and sends it to the query owner.

The standing queries may consist of data arrayed as XML schemas XML DTD s SQL queries Java scripts and other content and or computational profiling arrangements both standard and proprietary.

The last two queries are difficult to express in conventionally available systems. In particular conventional data vendors put the responsibility of identifying corporate subsidiaries on inquirers.

As a new trade report is received transmit processor computes the result formats it and distributes it.

At step transmit processor writes an audit trail record reflecting its transmission s of the new data.

At step a user sends a query to CCDM . One instance of a query is a request for trades in a security that occurred in a particular time interval. A further instance of a query is a request for a U3id associated with a security. Another instance of a query is a request for error reimbursement.

In some embodiments queries are created using web pages at a web site provided by web server drop down menus radio button and so on ensuring that the query is likely to be in proper form. In other embodiments queries are created using a query language and submitted via an application programming interface from the querying entity s computer. In other embodiments queries are provided in a natural language format and CCDM assists in converting natural language format to the internal format used in standing queries database .

At step analysis processor validates the query including whether the query owner is authorized to inquire about this data and whether the query syntax and content is correct.

At step analysis processor applies data rules to generate a response to the query. In some cases analysis processor refers the query to an administrator at CCDM . For instance decisions on error reimbursement must be manually approved by a CCDM administrator. Many requests for error reimbursement also require manual intervention by a CCDM administrator to resolve circumstances contributing to the error. Some requests for error reimbursement can be resolved automatically such as errors due to a computer malfunction by the CCDM when the computer malfunction was previously known to the CCDM.

In semantic network is provided. Standing queries are stored in standing queries database which may be a single data storage device or an array of data storage device in semantic network . Query processor is a single processor or a plurality of coupled processors resides in semantic network and serves to compare data received from transmit processor with the standing queries and to provide responses to the query owners. Semantic network is capable of content routing. Content based routing is explained in U.S. Patent Publication No. 2002 0150093 Ott the disclosure of which is hereby incorporated by reference in its entirety.

CCDM uses an interactive network software application supported by specialized scalable content routers query processor with embedded XML or other schemas representing all potential reference data content requests of all assembled financial transactions. Query processor deployed within semantic network overlaid on communication network includes an algorithm that allows for content selection content routing and load balancing. The router software allows for the network to select the path that a message will follow to its destination through setting of user controlled profiles within the router which interrogating the content of an XML or other schema defined message. The user need only send his her profile in this case in the form of a request for a specific reference data set to the nearest router. The routers talk to each other and exchanges aggregated profiles. A message packet is distributed through the network because each router knows the interest of its neighbor routers and they know their neighbors profile. The software dynamically adjusts the filtering between any two contiguous nodes in the network thus allowing for dynamic load balancing and scaling. Packets may travel through multiple routers and each router makes a decision on what to do with it. The routers operate within a multicast network. A message will be delivered to multiple users if it matches multiple profiles.

The matching of user defined profiles to the message content is done by the algorithm which operates on the entire schema for the message resident in the specialized router software. It matches an interest profile standing query that is a subset of the schema as represented by a user controlling the selection as specified in the same schema as the message. The message that passes the query will be forwarded otherwise not.

A forwarded message represents a validated string of reference data and this invention will calculate a unique encrypted tag number in one such embodiment Tag No. Modulus 10 11 calculation random number combining the bit values of reference data content with a random number and place the resulting number in a tagged field. It will then be logged and carried along with the transaction for audit purposes in validating a warranty request on any failed transactions. Also note that the network is schema agnostic. If end users agree on a new schema it can be implemented immediately nothing needs to be changed inside the network.

The router software separates a message into a header and an optional payload . If the message is unstructured the header contains a content descriptor if the message is for example a structured XML message it can go fully into the header. The distinction between header and payload simply defines what the router uses for its routing decision.

The benefit of this solution is that the heavy lifting of selection of data is done in the network where large bandwidth abounds vs. maintaining user profiles at a centralized server as in . Also by raising the abstraction level of what a network can do the cost of building and maintaining applications are greatly reduced. Previously a network could only deliver to a specific terminal address. If required to build a data centric solution multiple layers of middle ware are required on top of the network. This solution allows data abstraction within the network and routing directly to the application.

Secondly in an overnight or periodic updating mode such information as closing valuation prices for example every financial instrument master record is updated gets stored at the central store of all reference data the CCDM Data Pool as well as in the downstream distributed data stores specific to each organization.

Finally the central store of reference data at the CCDM Data Pool is both dynamically and periodically being updated by various suppliers and creators of the basic information of reference data. For example a notification is received that on a certain date Hewlett Packard will acquire Compaq or that as of a specific date the holders of stock in Company X will now have twice the number of shares due to a 100 stock dividend or that one dealer went out of business or that a new futures exchange is starting up or a new company is assigned a trading symbol and ID number or that an exchange will be closed on a certain date etc. Further internally contained reference data triggers events such as in a financial instruments master record containing information as to a conversion date and conversion rate for a bond the next reset date for a swap or the approaching ex date for a stock dividend. All such changes will be broadcast to also find its way downstream to the distributed data stores. Over time the separate downstream stores of reference data will be eliminated as more business application are written or modified to access the central store of reference data the CCDM Data Pool and the central store of information will be distributed across the network.

At step semantic network checks whether there are any standing queries relevant to the data. If so at step semantic network generates a response and sends it to the query owner.

A prospectus offering memorandum financial event announcement incorporation or business organizational documents ISDA master agreement and other such paper document is conceived and developed at the origins of a business formation financial transaction and or financial event. It is embodied in a digital document compatible with standard computer machine processed formats. It is subsequently transformed by standard mapping software into an extensible markup language XML format. This format in the some embodiments is XBRL. Using a predesigned XBRL taxonomy the data elements are transformed through mapping software from human readable word processed data into machine readable content at an elemental level. The data in transformed XBRL format is tagged with meaningful data names and with the first instance of the tag i.e. etc and then again the second instance of the identical tag such tag being unique unambiguous consistent and universal. The actual Business Entity Identifier Financial Event Identifier and Financial Instrument Identifier is a number of variable length assigned by the business entity or its designated agent after applying for such identity through a global registry which is the designated assigner of such identities. Such number also unique unambiguous consistent and universal is placed within the first and second instance of the tag.

The tagged data is transmitted via communication lines to the central storage device of the CCDM where it is filed in a computer storage medium with other information similarly sourced and communicated. The identity keys are linked to unique unambiguous and universal descriptions in human readable language for describing the instrument business entity and financial event in standardized abbreviated form. It is further linked to a symbol. In similar manner information about supply chain participants legal business hierarchies of the business entity and their role in the supply chain is further described in unique unambiguous and universal manner through other coding conventions that is part of this invention. The identification numbers are used as the storage key by the computer storage device for later retrieval by other component systems and methods of this invention.

Additional information will be maintained in a computer storage device of CCDM Data Pool connected by a communication device to the CCDM s Registry linked by identity keys and or symbol. Such information as the full official description of the financial instrument its terms and conditions its trading venue s and or listing markets it s currencies of trade its place and currency of settlement and other such data attributes of the financial instrument will be stored as reference data in CCDM Data Pool. Similar fuller information about business entities and their legal hierarchies and financial events and their relationship to financial instruments and business entities are also stored in CCDM Data Pool. Other data pools are maintained by commercial redistributors of reference data and linked to CCDM Registry in CCDM Data Pool to synchronize their identifiers so they can maintain all manner of supplemental data including to be made available to all others who have synchronized their data identifiers to the CCDM Registry.

At step investment banker requests a U3id for a new securities issue providing the symbol for the new security obtained from trading platform and the security name to CCDM .

At step CCDM provides the new U3id. Also CCDM distributes the new U3id to all parties who have indicated interest in being informed of new U3ids namely Firm A Firm B Registrar Bank depository and clearing corporation . Other parties can query CCDM to obtain the new U3id once they are aware of the symbol.

Having CCDM be the source of U3id and able to provide it in a variety of ways to a variety of data consumers eliminates prior art errors due to manual entry confusion with other securities and so on.

It will be recalled that illustrates an error in which clearing corporation has stored the wrong company name for the identifier. The error illustrated in is highly unlikely to occur when CCDM is in use because CCDM is the sole source of U3id identifiers and distributes the U3id with the proper company name. Clearing corporation receives this information automatically as shown at step and so is highly unlikely to err in associating the company name with its U3id.

It will be recalled that illustrates an error in which clearing corporation has mistakenly determined that the ex dividend date for XYZ is T 4 whereas the correct dividend date is T 3. When using CCDM this error is avoided because the announcement of the dividend date is distributed on a data feed from CCDM along with computer readable metadata identifying the correct ex dividend date as shown in step avoiding the manual errors that occur when a clerk tries to convert the conventional notice shown in Table 1 to digital form.

It will be recalled that illustrates an error in which investment manager has the wrong custodian bank associated with mutual funds AA BB and CC.

At a minimum when using CCDM investment manager can quickly query CCDM for the correct custodian bank and send revised notices without having to call its client.

In an improved scenario investment manager as an interested party automatically receives a notice of a change in custodian bank as shown in step . Since CCDM provides notifications in a uniform manner it is more likely than investment manager even if a small entity will be configured to properly receive and apply such notices.

In a further improved scenario third parties make software available to investment manager that automatically records and applies the notices from CCDM so that investment manager always sends its allocate message to the current custodian bank entirely eliminating the error shown in . In the conventional situation each client of investment manager can have its own data formats so it is difficult to automate reception of routine messages. In contrast using CCDM as an industry wide utility makes it cost effective for software providers to offer programs that automatically support investment manager .

It will be recalled that illustrates a prior art inter firm data aggregation problem caused by data vendors supplying respectively different closing prices for the same security. This problem is eliminated through use of CCDM . Thus the data from the various firms are commensurate enabling securities regulator to do a better job as she has a more accurate picture of what is happening.

CCDM is useful for eliminating or attenuating other data errors that occur in the financial industry in addition to the errors discussed above.

CCDM guarantees to its users that their trades will not fail to match due to problems with data from CCDM . More specifically if an error does occur based on properly using data from CCDM CCDM reimburses the customer for the costs associated with the error. The costs include covering the mismatched trade or the difference between the actual sale price and the correct sale price.

Matching errors are not expected just errors that are created through errors omissions breaches of security computer failure clerical faults etc. within the CCDM and externally through weather and catastrophic events such as hurricanes floods fires etc. The data errors that occur conventionally i.e. errors due to improper reference data failed transactions because a proprietary identifier was created for a security a valuation was wrong because a closing price was not recorded properly are eliminated or mitigated by CCDM . However should errors occur the CCDM must be prepared to support the losses and thus must set aside capital for such improbable eventualities unexpected losses . A client notifies CCDM that a transaction failed to be aggregated or matched and that the identifiers used came from CCDM . These identifiers had to have been previously certified as U3 compliant for the CCDM to be involved. An investigation tracks back through audit data .

As a risk mitigating infrastructure utility CCDM adheres to international norms of capital for unexpected losses not covered by reserves insurance etc. CCDM determines the capital reserve for losses also referred to as operational risk capital using the Advanced Measurement Approach AMA . CCDM is not the normal financial institution that the AMA is prescribed for.

Under the basic approach to modeling operational risk really a collection of many different stochastic techniques referred to as the loss distribution approach LDA banks estimate for each business line risk type cell or group thereof the likely distribution of operational risk losses over some future horizon bank regulators require a one year period . The Value at Risk VaR and resulting capital charge from these calculations is based on a high percentile of the loss distribution bank regulators require a 99.9 confidence level . This overall loss distribution is typically generated based on assumptions about the likely frequency and severity of operational risk loss events. In particular LDA s usually involve estimating the shape of the distributions of both the number of loss events and the severity of individual events. These estimates may involve imposing specific distributional assumptions i.e. a Poisson distribution for the number of loss events and a log normal distribution for the severity of individual events or deriving the distributions empirically through techniques such as boot strapping and Monte Carlo simulation.

An overall capital charge may be based on the simple sum of the operational risk VaR for each business line risk type combination which implicitly assumes perfect correlation of losses across these cells or by using other aggregation methods that recognize the risk reducing impact of less than full correlation.

Presently for operational risk there are several LDA methods being developed and no industry standard has yet emerged. Generally an LDA model is a quantitative methodology for assigning dollar values to expected and unexpected losses.

The output of a typical LDA model consists of 1 The Expected Loss EL which is the average loss as calculated from the cumulative loss distribution and 2 The Value at Risk VaR which summarizes the worst loss over a target horizon one year within a given confidence interval e.g. 99.9 percent. The statistical accuracy of the VaR number depends on the number of data points and or simulations. The more simulations or data points loss history the more accurate the result will be.

The error claimant goes to the website provided by website server signs in to their account using a password and possibly another identifier such as a biometric or token then selects File a Claim for Error Reimbursement from a menu of things that the claimant is authorized to do.

CCDM presents the claimant with a screen display for supplying information about their claim. The screen display asks for the U3id associated with the transaction. CCDM checks whether the claimant has a relationship to this transaction. If the claimant or the claimant s employer is not associated with the transaction then CCDM will not proceed so that the claimant will have to call customer service.

If the claimant is authorized to file a claim for this transaction CCDM presents the claimant with the known transaction details. CCDM then provides a drop down menu so that the claimant can identify the error. The screen display also has fields so that the claimant can explain how the error was noticed their judgment as to the reason for the error the amount of the claim and how the amount was determined.

In some cases CCDM knows of a situation that would result in the error and can automatically confirm that this transaction was affected by the situation and calculate the expected claim. If the requested claim is less than or equal to the expected claim CCDM automatically suggests to an administrator that the reimbursement request be approved.

In other cases CCDM is unable to automatically process the request and provides it to an administrator for manual resolution. The administrator uses audit data static data and dynamic data to research the transaction and may telephone or email the claimant for more information.

When the reimbursement request is approved the error is added to loss history data and CCDM automatically provides funds to the account of the claimant either directly or via transferring from the capital account for CCDM maintained at clearing corporation .

At a predetermined interval generally determined by regulatory reporting requirements such as monthly CCDM executes a program for determining the proper amount of funds for its capital account. The program operates as follows.

Along with reserves for expected losses and the cost of insurance for such items as errors and omissions fires and thefts wind and flood damage computer and utilities failure terrorist and privacy breaches and other catastrophic events the economic capital of the CCDM will be calculated for covering 99.9 of the overall losses Expected EL and Unexpected UL .

The initial assumption about the CCDMs Capital at Risk calculation will be based exclusively on assessing capital for Operational Risk. This initial assessment recognizing no loss history is yet available will be computed at an industry accepted standard of 12 of equivalent Financial Market Utility overall capital such utilities having credit and market risk in addition to operational risk the singular risk that the CCDM incurs. Thus for a 2 billion capital requirement overall for an equivalent operation incurring all three risk categories the single operational risk capital for the CCDM initially is to be computed at 240 million.

In some embodiments at step 7 use the total area under the curve divided by the total area of the curve and then multiple the resulting fraction by the total value of losses accumulated as displayed and summed from the histograms.

In other embodiments other techniques are used as described in U.S. patent application Ser. No. 12 081 619 filed Apr. 18 2008 having a common inventor herewith the disclosure of which is hereby incorporated by reference.

Although illustrative embodiments of the present invention and various modifications thereof have been described in detail herein with reference to the accompanying drawings it is to be understood that the invention is not limited to this precise embodiment and the described modifications and that various changes and further modifications may be effected therein by one skilled in the art without departing from the scope or spirit of the invention as defined in the appended claims.

