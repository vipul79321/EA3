# IRS Taxpayer Representation Flowcharts

## Complete Decision Guide for Enrolled Agents

*Based on PassKey EA Review Part 3: Representation - Units 2-8 (May 2025 - February 2026 Testing Cycle)*

---

## Table of Contents

1. [Master Representation Lifecycle](#master-representation-lifecycle)
2. [Who Can Practice Before the IRS](#1-who-can-practice-before-the-irs)
3. [Authorization Form Selection](#2-authorization-form-selection)
4. [Form 2848 Power of Attorney Guide](#3-form-2848-power-of-attorney-guide)
5. [Circular 230 Duties and Obligations](#4-circular-230-duties-and-obligations)
6. [Due Diligence Requirements](#5-due-diligence-requirements)
7. [Preparer Penalty Assessment](#6-preparer-penalty-assessment)
8. [OPR Disciplinary Process](#7-opr-disciplinary-process)
9. [Innocent and Injured Spouse Relief](#8-innocent-and-injured-spouse-relief)
10. [Taxpayer Bill of Rights](#9-taxpayer-bill-of-rights)
11. [Conflict of Interest Resolution](#10-conflict-of-interest-resolution)

---

## Master Representation Lifecycle

This flowchart shows the complete lifecycle of taxpayer representation from engagement through potential disciplinary action.

```mermaid
flowchart TD
    subgraph Engage["PHASE 1: ENGAGEMENT"]
        Client[Client Seeks<br/>Representation] --> PractCheck{Is Practitioner<br/>Authorized?}
        PractCheck -->|Yes| PractType{Practitioner<br/>Type?}
        PractCheck -->|No| CannotRep[Cannot Represent<br/>Before IRS]
        PractType -->|EA/CPA/Attorney| Unlimited[UNLIMITED<br/>PRACTICE RIGHTS]
        PractType -->|AFSP/Unenrolled| LimitedPract[LIMITED<br/>PRACTICE RIGHTS]
        PractType -->|ERPA/Actuary| SpecialPract[SPECIALIZED<br/>PRACTICE RIGHTS]
    end

    subgraph Auth["PHASE 2: AUTHORIZATION"]
        Unlimited --> AuthNeeded{Authorization<br/>Needed?}
        LimitedPract --> AuthNeeded
        AuthNeeded -->|Full Representation| Form2848[File Form 2848<br/>Power of Attorney]
        AuthNeeded -->|Info Only| Form8821[File Form 8821<br/>Tax Info Authorization]
        Form2848 --> CAF[CAF Number<br/>Assigned]
    end

    subgraph Practice["PHASE 3: ACTIVE REPRESENTATION"]
        CAF --> Represent[Represent Client<br/>Before IRS]
        Form8821 --> ViewInfo[View/Receive<br/>Client Information]
        Represent --> Circ230{Follow<br/>Circular 230?}
        Circ230 -->|Yes| GoodStanding[Maintain Good<br/>Standing]
        Circ230 -->|No| Violation[Potential<br/>Violation]
    end

    subgraph Discipline["PHASE 4: DISCIPLINARY"]
        Violation --> OPR[OPR<br/>Investigation]
        OPR --> Sanction{Sanction<br/>Imposed?}
        Sanction -->|Censure| Censure[Public Reprimand<br/>Can Continue]
        Sanction -->|Suspension| Suspend[Temporary Bar<br/>Cannot Practice]
        Sanction -->|Disbarment| Disbar[Permanent Bar<br/>Must Reapply]
        Sanction -->|Monetary| MoneyPen[Financial<br/>Penalty]
    end

    subgraph Prepare["PHASE 5: RETURN PREPARATION"]
        GoodStanding --> PrepReturn[Prepare<br/>Tax Returns]
        PrepReturn --> DueDiligence{Due Diligence<br/>Required?}
        DueDiligence -->|EITC/CTC/AOTC/ODC/HOH| Form8867[Complete<br/>Form 8867]
        DueDiligence -->|No| SignReturn[Sign and<br/>File Return]
        Form8867 --> SignReturn
    end
```

---

## 1. Who Can Practice Before the IRS

### Practitioner Authority Decision Tree

```mermaid
flowchart TD
    subgraph Question["CLIENT NEEDS REPRESENTATION"]
        Start[Client Needs Help<br/>Before IRS] --> MatterType{What Type<br/>of Matter?}
    end

    subgraph Unlimited["UNLIMITED PRACTITIONERS"]
        MatterType -->|Any IRS Matter| UnlimitedList[Unlimited Practitioners:<br/>- Enrolled Agents EA<br/>- CPAs<br/>- Attorneys]
        UnlimitedList --> UnlimitedScope[Can Represent:<br/>- All IRS offices<br/>- All tax matters<br/>- Audits, Appeals, Collections<br/>- Tax Court]
    end

    subgraph Limited["LIMITED PRACTITIONERS"]
        MatterType -->|Return They Prepared| LimitedCheck{Practitioner<br/>Type?}
        LimitedCheck -->|AFSP Participant| AFSPScope[AFSP Can Represent:<br/>- Revenue Agents<br/>- Customer Service<br/>ONLY for returns prepared]
        LimitedCheck -->|Unenrolled Preparer| UnenrolledScope[Unenrolled Can Represent:<br/>- Revenue Agents<br/>- Customer Service<br/>ONLY for returns prepared]
        LimitedCheck -->|Neither| CannotRep2[CANNOT Represent<br/>Must Refer to<br/>Unlimited Practitioner]
    end

    subgraph Special["SPECIALIZED PRACTITIONERS"]
        MatterType -->|Actuarial Matters| ActuaryScope[Enrolled Actuary<br/>Actuarial Matters Only]
        MatterType -->|Retirement Plans| ERPAScope[ERPA<br/>Retirement Plan Matters Only]
    end

    subgraph Other["OTHER AUTHORIZED"]
        MatterType -->|LITC/VITA Program| StudentScope[Students/Law Grads<br/>Within Program Only]
        MatterType -->|Family Member| FamilyScope[Immediate Family<br/>Individuals Only<br/>Not Businesses]
    end
```

### Practitioner Comparison Table

| Practitioner | Practice Rights | Where Can Represent | Limitations |
|--------------|-----------------|---------------------|-------------|
| **Enrolled Agent (EA)** | Unlimited | All IRS offices | None |
| **CPA** | Unlimited | All IRS offices | None |
| **Attorney** | Unlimited | All IRS offices | None |
| **AFSP Participant** | Limited | Revenue Agents, Customer Service | Returns they prepared only |
| **Unenrolled Preparer** | Very Limited | Revenue Agents, Customer Service | Returns they prepared only |
| **ERPA** | Limited | IRS | Retirement plan matters only |
| **Enrolled Actuary** | Limited | IRS | Actuarial matters only |
| **Student (LITC/VITA)** | Limited | Within program | Program matters only |
| **Family Member** | Limited | IRS | Individual taxpayers only |

---

## 2. Authorization Form Selection

### Form Selection Decision Tree

```mermaid
flowchart TD
    subgraph Need["WHAT DOES CLIENT NEED?"]
        Start[Determine Client<br/>Authorization Needs] --> FullRep{Need Full<br/>Representation?}
    end

    subgraph POA["POWER OF ATTORNEY"]
        FullRep -->|Yes| POAPath[Form 2848<br/>Power of Attorney]
        POAPath --> POAFeatures[Form 2848 Allows:<br/>- Speak for client<br/>- Receive confidential info<br/>- Sign agreements<br/>- Receive refund checks<br/>- Substitute/add representatives]
        POAFeatures --> POADuration[Duration:<br/>Until revoked or<br/>7 years from signature]
    end

    subgraph TIA["TAX INFORMATION AUTHORIZATION"]
        FullRep -->|No| InfoOnly{Just Need<br/>Information?}
        InfoOnly -->|Yes| TIAPath[Form 8821<br/>Tax Information Authorization]
        TIAPath --> TIAFeatures[Form 8821 Allows:<br/>- Receive tax info<br/>- Inspect/receive copies<br/>- Discuss return with IRS]
        TIAFeatures --> TIALimits[Form 8821 Does NOT Allow:<br/>- Represent taxpayer<br/>- Sign anything<br/>- Receive refunds<br/>- Advocate for client]
    end

    subgraph TPD["THIRD PARTY DESIGNEE"]
        InfoOnly -->|No| QuickQ{Quick Question<br/>About Filed Return?}
        QuickQ -->|Yes| TPDPath[Third Party Designee<br/>Checkbox on Return]
        TPDPath --> TPDFeatures[Checkbox Allows:<br/>- Answer questions about return<br/>- Receive missing info notices<br/>- Valid 1 year from due date]
    end

    subgraph Oral["ORAL AUTHORIZATION"]
        QuickQ -->|No| OralPath[Oral Authorization<br/>During IRS Call]
        OralPath --> OralFeatures[Oral Allows:<br/>- One-time disclosure<br/>- Duration of call only<br/>- IRS authenticates first]
    end
```

### Authorization Forms Comparison

| Feature | Form 2848 (POA) | Form 8821 (TIA) | Third Party Designee |
|---------|-----------------|-----------------|---------------------|
| **Represent client** | Yes | No | No |
| **Receive info** | Yes | Yes | Limited |
| **Sign documents** | Yes | No | No |
| **Receive refunds** | Yes (if specified) | No | No |
| **Duration** | Until revoked/7 years | Until revoked | 1 year |
| **CAF number** | Yes | Optional | No |
| **Substitute rep** | Yes | No | No |

---

## 3. Form 2848 Power of Attorney Guide

### Form 2848 Completion Flowchart

```mermaid
flowchart TD
    subgraph Line1["LINE 1: TAXPAYER INFORMATION"]
        Start[Begin Form 2848] --> TaxpayerInfo[Enter Taxpayer:<br/>- Name<br/>- SSN/EIN<br/>- Address<br/>- Daytime phone]
    end

    subgraph Line2["LINE 2: REPRESENTATIVE"]
        TaxpayerInfo --> RepInfo[Enter Representative:<br/>- Name and address<br/>- CAF number if known<br/>- PTIN<br/>- Phone and fax]
        RepInfo --> Designation{Representative<br/>Designation?}
        Designation -->|Attorney| DesigA[a - Attorney]
        Designation -->|CPA| DesigB[b - CPA]
        Designation -->|EA| DesigC[c - Enrolled Agent]
        Designation -->|Officer| DesigD[d - Officer of taxpayer]
        Designation -->|Family| DesigE[e - Family member]
        Designation -->|ERPA| DesigF[f - Enrolled Retirement Plan Agent]
        Designation -->|Other| DesigOther[g-k - Other categories]
    end

    subgraph Line3["LINE 3: TAX MATTERS"]
        DesigA --> TaxMatters[Specify Tax Matters:<br/>- Tax form number<br/>- Tax periods<br/>- Specific matter if applicable]
        DesigB --> TaxMatters
        DesigC --> TaxMatters
        DesigD --> TaxMatters
        DesigE --> TaxMatters
        DesigF --> TaxMatters
        DesigOther --> TaxMatters
    end

    subgraph Line4["LINE 4: SPECIFIC ACTS"]
        TaxMatters --> SpecificActs{Authorize<br/>Specific Acts?}
        SpecificActs -->|Receive Refund| RefundAuth[Check box for<br/>refund authorization]
        SpecificActs -->|Sign Return| SignAuth[Check box for<br/>signing authority]
        SpecificActs -->|Substitute Rep| SubAuth[Check box for<br/>substitute authority]
        SpecificActs -->|None| NoSpecial[Leave blank]
    end

    subgraph Line5_7["LINES 5-7: ADDITIONAL"]
        RefundAuth --> AdditionalReps[Line 5: Additional<br/>Representatives if needed]
        SignAuth --> AdditionalReps
        SubAuth --> AdditionalReps
        NoSpecial --> AdditionalReps
        AdditionalReps --> Retention[Line 6: Retention of<br/>prior POAs or revoke]
        Retention --> CAFNote[Line 7: Notices to be<br/>sent to representative]
    end

    subgraph Signature["SIGNATURE SECTION"]
        CAFNote --> TaxpayerSign[Taxpayer Signature<br/>and Date REQUIRED]
        TaxpayerSign --> RepSign[Representative Declaration<br/>Under Penalties of Perjury]
        RepSign --> Submit[Submit to IRS<br/>Fax: 855-214-7519]
    end
```

### Acts Authorized vs. Not Authorized by POA

| Authorized (Unless Limited) | NOT Authorized (Must Specify) |
|----------------------------|------------------------------|
| Receive confidential information | Receive refund checks |
| Inspect/receive copies | Sign tax return |
| Perform any acts taxpayer can | Substitute another representative |
| Represent before all IRS offices | Execute waivers |
| Sign agreements (except returns) | Sign closing agreements |
| Execute consents to extend SOL | Execute offers in compromise |

---

## 4. Circular 230 Duties and Obligations

### Complete Circular 230 Duties Map

```mermaid
flowchart TD
    subgraph ClientDuties["DUTIES TO CLIENTS - Subpart B"]
        CD1[Competence<br/>Must have knowledge and skill]
        CD2[Diligence<br/>Prompt and thorough service]
        CD3[Return Records<br/>Must return on request]
        CD4[Reasonable Fees<br/>Cannot charge unconscionable fees]
        CD5[No Conflicts<br/>Cannot represent conflicting interests]
        CD6[Written Fee Agreement<br/>Recommended for contingent fees]
    end

    subgraph IRSDuties["DUTIES TO IRS - Subpart B"]
        ID1[Accurate Submissions<br/>All documents must be correct]
        ID2[No Delay<br/>Cannot unreasonably delay]
        ID3[Assist Compliance<br/>Help with lawful requests]
        ID4[Due Diligence<br/>Verify accuracy of submissions]
        ID5[No Misleading<br/>Cannot mislead IRS]
        ID6[Inform of Errors<br/>Advise client of errors/omissions]
    end

    subgraph Prohibited["PROHIBITED CONDUCT - Subpart B"]
        PC1[Negotiating Client Refund Checks<br/>Cannot endorse or cash]
        PC2[False Advertising<br/>No misleading statements]
        PC3[Uninvited Solicitation<br/>Limited to written mail]
        PC4[Contingent Fees<br/>Prohibited for most returns]
        PC5[Practice While Suspended<br/>Absolutely prohibited]
        PC6[Assist Disbarred<br/>Cannot help suspended practitioners]
    end

    subgraph Standards["PRACTICE STANDARDS - Subpart B"]
        PS1[Return Positions<br/>Substantial authority required]
        PS2[Advised of Penalties<br/>Must inform client]
        PS3[Written Advice<br/>Consider all facts]
        PS4[Reliance on Others<br/>Cannot ignore known facts]
        PS5[Knowledge of Error<br/>Must advise correction]
    end
```

### Circular 230 Violations and Sanctions

```mermaid
flowchart TD
    subgraph Violations["TYPES OF VIOLATIONS"]
        V1[Incompetence or<br/>Disreputable Conduct]
        V2[Willful Violation<br/>of Regulations]
        V3[Reckless Conduct<br/>Resulting in Harm]
        V4[False or Misleading<br/>Statements to IRS]
        V5[Contemptuous Conduct<br/>Before IRS]
        V6[Knowingly Assist<br/>Disbarred Practitioner]
    end

    subgraph Investigation["OPR INVESTIGATION"]
        V1 --> OPR[Office of<br/>Professional Responsibility]
        V2 --> OPR
        V3 --> OPR
        V4 --> OPR
        V5 --> OPR
        V6 --> OPR
    end

    subgraph Sanctions["POSSIBLE SANCTIONS - Subpart C"]
        OPR --> SanctionType{Severity of<br/>Violation?}
        SanctionType -->|Minor| Censure[CENSURE<br/>Public reprimand<br/>Can continue practice]
        SanctionType -->|Moderate| Suspension[SUSPENSION<br/>Temporary bar<br/>Specified period]
        SanctionType -->|Severe| Disbarment[DISBARMENT<br/>Cannot practice<br/>May apply for reinstatement]
        SanctionType -->|Financial| Monetary[MONETARY PENALTY<br/>Up to 100% of gross income<br/>from engagement]
    end

    subgraph Expedited["EXPEDITED SUSPENSION"]
        Expedited1[Practitioner shown to have:<br/>- Lost license<br/>- Been convicted of crime<br/>- Posed threat to IRS]
        Expedited1 --> ImmediateSuspend[Immediate Suspension<br/>Pending Full Hearing]
    end
```

---

## 5. Due Diligence Requirements

### Due Diligence Compliance Flowchart

```mermaid
flowchart TD
    subgraph Trigger["WHEN IS DD REQUIRED?"]
        Return[Preparing Tax Return] --> Credits{Does Return Claim?}
        Credits -->|EITC| DDRequired[Due Diligence<br/>REQUIRED]
        Credits -->|CTC/ACTC| DDRequired
        Credits -->|AOTC| DDRequired
        Credits -->|ODC| DDRequired
        Credits -->|HOH Status| DDRequired
        Credits -->|None of These| NoDDReq[No DD Requirements<br/>for This Return]
    end

    subgraph FourReqs["FOUR DD REQUIREMENTS"]
        DDRequired --> Req1[Requirement 1:<br/>Complete Form 8867<br/>Paid Preparer DD Checklist]
        Req1 --> Req2[Requirement 2:<br/>Complete Applicable Worksheets<br/>Or equivalent documentation]
        Req2 --> Req3[Requirement 3:<br/>Make Reasonable Inquiries<br/>Ask questions, document answers]
        Req3 --> Req4[Requirement 4:<br/>Retain Records 3 Years<br/>Form 8867, worksheets, notes]
    end

    subgraph Compliance["COMPLIANCE CHECK"]
        Req4 --> AllMet{All Four<br/>Requirements Met?}
        AllMet -->|Yes| Compliant[Due Diligence<br/>SATISFIED]
        AllMet -->|No| PenaltyRisk[PENALTY EXPOSURE<br/>$635 per failure<br/>per credit/status]
    end

    subgraph Penalty["PENALTY CALCULATION"]
        PenaltyRisk --> Example[Example:<br/>Return claims EITC + CTC + HOH<br/>Failed all DD = 3 × $635 = $1,905]
    end
```

### Form 8867 Requirements by Credit/Status

```mermaid
flowchart TD
    subgraph EITC["EITC REQUIREMENTS"]
        EITC1[Verify:<br/>- Valid SSN for taxpayer/spouse<br/>- Valid SSN for qualifying child<br/>- AGI limits<br/>- Investment income limit<br/>- Filing status requirements]
    end

    subgraph CTC["CTC REQUIREMENTS"]
        CTC1[Verify:<br/>- Qualifying child definition<br/>- Age under 17<br/>- Relationship test<br/>- Residency test<br/>- Support test<br/>- Citizenship/SSN]
    end

    subgraph AOTC["AOTC REQUIREMENTS"]
        AOTC1[Verify:<br/>- Eligible student status<br/>- First 4 years of postsecondary<br/>- At least half-time enrollment<br/>- Qualified expenses<br/>- No felony drug conviction]
    end

    subgraph ODC["ODC REQUIREMENTS"]
        ODC1[Verify:<br/>- Qualifying relative<br/>- Not claimed as QC elsewhere<br/>- Support test<br/>- Gross income test<br/>- Citizenship/residency]
    end

    subgraph HOH["HOH REQUIREMENTS"]
        HOH1[Verify:<br/>- Unmarried or considered unmarried<br/>- Paid over half cost of home<br/>- Qualifying person lived with<br/>  taxpayer more than half year]
    end
```

### Due Diligence Penalty Summary

| Credit/Status | Penalty (2024) | What Must Be Verified |
|---------------|----------------|----------------------|
| EITC | $635 | Income, SSN, qualifying children, residency |
| CTC/ACTC | $635 | Qualifying child, age, relationship, SSN |
| AOTC | $635 | Student status, enrollment, expenses |
| ODC | $635 | Qualifying relative, support, income |
| HOH | $635 | Marital status, qualifying person, costs |
| **Multiple on same return** | $635 × each | Each credit/status counted separately |

---

## 6. Preparer Penalty Assessment

### IRC §6694 Penalty Flowchart

```mermaid
flowchart TD
    subgraph Position["TAX POSITION ANALYSIS"]
        TaxPos[Tax Position<br/>on Return] --> Authority{Level of<br/>Authority?}
    end

    subgraph Substantial["SUBSTANTIAL AUTHORITY TEST"]
        Authority -->|Substantial Authority| Disclosed{Position<br/>Disclosed?}
        Authority -->|Less Than Substantial| NoAuthority[Insufficient<br/>Authority]
        Disclosed -->|Yes| ReasonableBasis{Reasonable<br/>Basis Exists?}
        Disclosed -->|No| NeedSubstantial[Need Substantial<br/>Authority]
        ReasonableBasis -->|Yes| NoPenalty6694[No Penalty<br/>Position OK]
        ReasonableBasis -->|No| Penalty6694a
    end

    subgraph TaxShelter["TAX SHELTER POSITIONS"]
        NoAuthority --> Shelter{Tax Shelter<br/>Position?}
        NeedSubstantial --> Shelter
        Shelter -->|Yes| MLTN{More Likely<br/>Than Not?}
        MLTN -->|Yes| NoPenaltyShelter[No Penalty<br/>For Shelter]
        MLTN -->|No| Penalty6694a[Section 6694a Penalty:<br/>Greater of $1,000 or<br/>50% of income from return]
        Shelter -->|No| Penalty6694a
    end

    subgraph Willful["WILLFUL OR RECKLESS"]
        WillfulAct[Willful Attempt to<br/>Understate Liability] --> Penalty6694b[Section 6694b Penalty:<br/>Greater of $5,000 or<br/>75% of income from return]
        RecklessAct[Reckless or Intentional<br/>Disregard of Rules] --> Penalty6694b
    end
```

### IRC §6695 Other Preparer Penalties

```mermaid
flowchart TD
    subgraph Penalties6695["IRC §6695 PENALTIES"]
        P1[6695a: Failure to Furnish Copy<br/>to Taxpayer] --> Amt1[$60 per failure<br/>Max $30,000/year]
        
        P2[6695b: Failure to Sign Return] --> Amt2[$60 per failure<br/>Max $30,000/year]
        
        P3[6695c: Failure to Include<br/>PTIN on Return] --> Amt3[$60 per failure<br/>Max $30,000/year]
        
        P4[6695d: Failure to Retain Copy<br/>or List of Returns] --> Amt4[$60 per failure<br/>Max $30,000/year]
        
        P5[6695e: Failure to File<br/>Correct Information Return] --> Amt5[$60 per failure<br/>Max $30,000/year]
        
        P6[6695f: Negotiating<br/>Refund Check] --> Amt6[$635 per check<br/>No maximum]
        
        P7[6695g: Due Diligence<br/>Failure] --> Amt7[$635 per failure<br/>No maximum]
    end
```

### Penalty Standards Summary

| Penalty | Amount | Trigger | Defense |
|---------|--------|---------|---------|
| §6694(a) Unreasonable Position | Greater of $1,000 or 50% of fee | Position lacks substantial authority | Reasonable cause + good faith |
| §6694(b) Willful/Reckless | Greater of $5,000 or 75% of fee | Willful understatement or reckless disregard | None |
| §6695(a)-(e) Administrative | $60 per failure | Failure to sign, furnish copy, include PTIN, etc. | Reasonable cause |
| §6695(f) Negotiating Check | $635 per check | Endorsing or cashing client refund | None |
| §6695(g) Due Diligence | $635 per credit/status | Failure to meet DD requirements | Reasonable cause |

---

## 7. OPR Disciplinary Process

### Complete OPR Process Flowchart

```mermaid
flowchart TD
    subgraph Initiation["CASE INITIATION"]
        Complaint[Complaint Received<br/>or Referral Made] --> Source{Source of<br/>Complaint?}
        Source -->|Public Complaint| Review1[OPR Reviews<br/>Complaint]
        Source -->|IRS Referral| Review1
        Source -->|Court Referral| Review1
        Source -->|State Board| Review1
    end

    subgraph Investigation["INVESTIGATION PHASE"]
        Review1 --> Merit{Does Complaint<br/>Have Merit?}
        Merit -->|No| Dismiss[Complaint<br/>Dismissed]
        Merit -->|Yes| Investigate[Full OPR<br/>Investigation]
        Investigate --> Evidence{Sufficient<br/>Evidence?}
        Evidence -->|No| CloseCase[Case Closed<br/>No Action]
        Evidence -->|Yes| Notice[Notice of Institution<br/>of Proceedings]
    end

    subgraph Response["PRACTITIONER RESPONSE"]
        Notice --> Answer{Practitioner<br/>Files Answer?}
        Answer -->|No Answer in 30 Days| Default[Default Judgment<br/>Against Practitioner]
        Answer -->|Files Answer| Conference[Pre-Hearing<br/>Conference]
        Conference --> Settle{Settlement<br/>Reached?}
        Settle -->|Yes| ConsentOrder[Consent to<br/>Sanction]
        Settle -->|No| Hearing[Formal Hearing<br/>Before ALJ]
    end

    subgraph Hearing["HEARING PHASE"]
        Hearing --> ALJReview[Administrative Law Judge<br/>Reviews Evidence]
        ALJReview --> ALJDecision[ALJ Issues<br/>Decision]
    end

    subgraph Appeal["APPEAL RIGHTS"]
        ALJDecision --> Appeal30{Appeal Within<br/>30 Days?}
        ConsentOrder --> Final1[Sanction<br/>Becomes Final]
        Default --> Final1
        Appeal30 -->|No| Final2[ALJ Decision<br/>Becomes Final]
        Appeal30 -->|Yes| Treasury[Appeal to<br/>Secretary of Treasury]
        Treasury --> TreasuryDecision[Treasury<br/>Decision]
        TreasuryDecision --> FedCourt{Seek Federal<br/>Court Review?}
        FedCourt -->|Yes| DistrictCourt[Limited Review<br/>in Federal Court]
        FedCourt -->|No| Final3[Treasury Decision<br/>Final]
    end
```

### Expedited Suspension Process

```mermaid
flowchart TD
    subgraph Triggers["EXPEDITED SUSPENSION TRIGGERS"]
        T1[Practitioner has been:<br/>- Convicted of tax crime<br/>- Lost professional license<br/>- Convicted of felony]
        T2[Practitioner poses<br/>threat to IRS or public]
        T3[Practitioner failed to<br/>comply with subpoena]
    end

    subgraph Process["EXPEDITED PROCESS"]
        T1 --> Motion[OPR Files Motion for<br/>Immediate Suspension]
        T2 --> Motion
        T3 --> Motion
        Motion --> ImmediateSuspend[Practitioner Immediately<br/>Suspended]
        ImmediateSuspend --> Response{Practitioner<br/>Responds?}
        Response -->|Within 10 Days| Hearing2[Expedited Hearing<br/>Within 40 Days]
        Response -->|No Response| SuspendContinues[Suspension<br/>Continues]
    end
```

### Sanction Levels

| Sanction | Definition | Effect | Reinstatement |
|----------|------------|--------|---------------|
| **Censure** | Public reprimand | Can continue practice | N/A - no suspension |
| **Suspension** | Temporary prohibition | Cannot practice for specified period | Automatic after period ends |
| **Disbarment** | Indefinite prohibition | Cannot practice | Must petition after 5 years |
| **Monetary** | Financial penalty | Up to 100% of gross income from engagement | N/A |

---

## 8. Innocent and Injured Spouse Relief

### Spouse Relief Decision Tree

```mermaid
flowchart TD
    subgraph Situation["SPOUSE SITUATION"]
        Joint[Filed Joint Return<br/>Tax Problem Exists] --> ProblemType{What Type<br/>of Problem?}
    end

    subgraph Understatement["UNDERSTATEMENT ISSUES"]
        ProblemType -->|Tax Understated<br/>Erroneous Item| Knowledge{Did Requesting Spouse<br/>Know of Error?}
        Knowledge -->|No Knowledge| InnocentReq{Meet ALL<br/>Innocent Spouse<br/>Requirements?}
        Knowledge -->|Had Knowledge| SeparationCheck{Divorced/Separated<br/>12+ Months?}
    end

    subgraph Innocent["INNOCENT SPOUSE - §6015(b)"]
        InnocentReq -->|Yes| InnocentRelief[Form 8857<br/>INNOCENT SPOUSE RELIEF<br/>Complete Relief from<br/>Joint Liability]
        InnocentReq -->|No| SeparationCheck
    end

    subgraph Separation["SEPARATION OF LIABILITY - §6015(c)"]
        SeparationCheck -->|Yes| SeparationRelief[Form 8857<br/>SEPARATION OF LIABILITY<br/>Allocate Deficiency<br/>Between Spouses]
        SeparationCheck -->|No| EquitableCheck{Would Holding<br/>Liable Be<br/>Inequitable?}
    end

    subgraph Equitable["EQUITABLE RELIEF - §6015(f)"]
        EquitableCheck -->|Yes| EquitableRelief[Form 8857<br/>EQUITABLE RELIEF<br/>Discretionary Relief<br/>IRS Considers All Factors]
        EquitableCheck -->|No| NoRelief[NO RELIEF<br/>AVAILABLE<br/>Jointly Liable]
    end

    subgraph Underpayment["UNDERPAYMENT ISSUES"]
        ProblemType -->|Tax Correct but<br/>Not Paid| EquitableOnly[Only EQUITABLE RELIEF<br/>Available for<br/>Underpayments]
        EquitableOnly --> EquitableRelief
    end

    subgraph Injured["INJURED SPOUSE"]
        ProblemType -->|Refund Offset for<br/>Spouse Debt| InjuredPath[Form 8379<br/>INJURED SPOUSE CLAIM<br/>Get Back YOUR Portion<br/>of Joint Refund]
    end
```

### Three Types of Innocent Spouse Relief Comparison

| Element | Innocent Spouse §6015(b) | Separation of Liability §6015(c) | Equitable Relief §6015(f) |
|---------|--------------------------|----------------------------------|---------------------------|
| **Form** | Form 8857 | Form 8857 | Form 8857 |
| **Problem Type** | Understatement | Understatement | Understatement OR Underpayment |
| **Knowledge** | No knowledge required | Can have knowledge | Considered as factor |
| **Marital Status** | Any | Divorced/separated 12+ months | Any |
| **Effect** | Full relief | Allocates liability | Full or partial relief |
| **Time Limit** | 2 years from collection | 2 years from collection | Varies |

### Injured Spouse vs. Innocent Spouse

```mermaid
flowchart TD
    subgraph Compare["INJURED VS INNOCENT"]
        Injured[INJURED SPOUSE<br/>Form 8379] --> InjuredSituation[Situation:<br/>Joint refund offset for<br/>OTHER spouse debt like:<br/>- Past due child support<br/>- Federal debt<br/>- State debt]
        
        Innocent[INNOCENT SPOUSE<br/>Form 8857] --> InnocentSituation[Situation:<br/>Joint liability exists for<br/>tax due to OTHER spouse<br/>erroneous items or fraud]
        
        InjuredSituation --> InjuredResult[Result:<br/>Get YOUR portion of<br/>refund returned]
        
        InnocentSituation --> InnocentResult[Result:<br/>Relieved from<br/>joint liability]
    end
```

---

## 9. Taxpayer Bill of Rights

### Ten Taxpayer Rights Visualization

```mermaid
flowchart TD
    subgraph Rights["10 TAXPAYER RIGHTS"]
        R1[1. RIGHT TO BE INFORMED<br/>Know what to do to comply]
        R2[2. RIGHT TO QUALITY SERVICE<br/>Prompt, courteous, professional]
        R3[3. RIGHT TO PAY NO MORE<br/>THAN CORRECT AMOUNT]
        R4[4. RIGHT TO CHALLENGE<br/>IRS Position and Be Heard]
        R5[5. RIGHT TO APPEAL<br/>In independent forum]
        R6[6. RIGHT TO FINALITY<br/>Know when IRS is finished]
        R7[7. RIGHT TO PRIVACY<br/>No more intrusive than necessary]
        R8[8. RIGHT TO CONFIDENTIALITY<br/>Info not disclosed improperly]
        R9[9. RIGHT TO RETAIN<br/>REPRESENTATION]
        R10[10. RIGHT TO FAIR AND<br/>JUST TAX SYSTEM]
    end

    subgraph Enforcement["ENFORCEMENT"]
        R1 --> TAS[Taxpayer Advocate Service<br/>Form 911]
        R2 --> TAS
        R3 --> TAS
        R4 --> TAS
        R5 --> TAS
        R6 --> TAS
        R7 --> TAS
        R8 --> TAS
        R9 --> TAS
        R10 --> TAS
    end
```

### Taxpayer Advocate Service (TAS)

```mermaid
flowchart TD
    subgraph When["WHEN TO USE TAS"]
        Criteria[TAS Criteria:<br/>- Significant hardship<br/>- Immediate adverse action<br/>- Cost exceeds benefit<br/>- Delay over 30 days<br/>- Did not receive response by date promised]
    end

    subgraph How["HOW TO REQUEST"]
        Criteria --> Form911[File Form 911<br/>Request for Taxpayer<br/>Advocate Service Assistance]
        Form911 --> Methods[Submission Methods:<br/>- Fax<br/>- Mail<br/>- Phone 877-777-4778<br/>- In person at local office]
    end

    subgraph Result["TAS ASSISTANCE"]
        Methods --> Assigned[Case Assigned to<br/>TAS Advocate]
        Assigned --> Assist[TAS Can:<br/>- Issue Taxpayer Assistance Orders<br/>- Stop IRS collection actions<br/>- Expedite case resolution<br/>- Advocate with IRS offices]
    end
```

---

## 10. Conflict of Interest Resolution

### Conflict of Interest Decision Tree

```mermaid
flowchart TD
    subgraph Identify["IDENTIFY POTENTIAL CONFLICT"]
        Situation[Engagement Request] --> ConflictCheck{Potential<br/>Conflict?}
    end

    subgraph Types["TYPES OF CONFLICTS"]
        ConflictCheck -->|Yes| ConflictType{Type of<br/>Conflict?}
        ConflictCheck -->|No| Accept[May Accept<br/>Engagement]
        
        ConflictType -->|Differing Interests| DifferingInt[Clients with<br/>Differing Interests]
        ConflictType -->|Personal Interest| PersonalInt[Personal Interest<br/>of Practitioner]
        ConflictType -->|Former Client| FormerClient[Former Client<br/>Adverse Interest]
    end

    subgraph Resolution["CONFLICT RESOLUTION"]
        DifferingInt --> WaiverPossible{Waiver<br/>Possible?}
        PersonalInt --> WaiverPossible
        FormerClient --> WaiverPossible
        
        WaiverPossible -->|Yes| ThreeReqs[All Three Required:<br/>1. Believe can provide competent<br/>   diligent representation to each<br/>2. Not prohibited by law<br/>3. Each client gives informed<br/>   written consent]
        
        WaiverPossible -->|No| MustDecline[Must Decline<br/>or Withdraw]
        
        ThreeReqs --> ConsentObtained{Written Consent<br/>Obtained?}
        ConsentObtained -->|Yes| CanRepresent[May Represent<br/>Multiple Clients]
        ConsentObtained -->|No| MustDecline
    end

    subgraph NoWaiver["CONFLICTS THAT CANNOT BE WAIVED"]
        NeverWaive[Cannot Waive:<br/>- Representation in same dispute<br/>- Clearly prohibited by law<br/>- Cannot provide competent representation]
    end
```

### Conflict Scenarios

| Scenario | Can Represent? | Requirements |
|----------|---------------|--------------|
| Husband and wife (same return) | Yes | Generally no conflict |
| Husband and wife (divorce) | No | Cannot represent both in same proceeding |
| Business partners (same matter) | Maybe | Written consent from both if interests differ |
| Former client vs. current | No | Adverse representation prohibited |
| Practitioner's personal interest | Maybe | Only if no material limitation on representation |

---

## Quick Reference: Key Forms

| Form | Name | Purpose |
|------|------|---------|
| **2848** | Power of Attorney | Full representation authority |
| **8821** | Tax Information Authorization | View information only |
| **8821-A** | Disclosure Authorization | Third-party disclosure for SB/SE |
| **8857** | Request for Innocent Spouse Relief | Innocent/separation/equitable relief |
| **8379** | Injured Spouse Allocation | Recover refund offset |
| **8867** | Paid Preparer's Due Diligence Checklist | DD for EITC/CTC/AOTC/ODC/HOH |
| **911** | Request for Taxpayer Advocate Service | Request TAS assistance |
| **12203** | Request for Appeals Review | Request Appeals conference |

---

*This flowchart guide is based on Circular 230 and IRS procedures current through December 31, 2024, as tested on the EA exam May 2025 - February 2026 cycle.*
