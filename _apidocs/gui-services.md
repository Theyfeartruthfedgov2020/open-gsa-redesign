---
title: GUI Services
banner-heading: GUI Services
---

<link rel="stylesheet" type="text/css" href="../../assets/swaggerui-dist/swagger-ui.css" >


## Overview
Legacy FPDS-NG offers Web Services to the Public Users to receive Contract and Referential data. 

* Public Users are the type of users that are not associated with a Federal Government agency and that do not post data to FPDS-NG.
* Public Users must send User ID, Password and Service Originator ID in their Web Service requests sent to legacy FPDS-NG.
* Legacy FPDS-NG allows Public User accounts (User Type = P) to be created with the default “General Public” role that will help them to access 
  “Final” Public and “Final” DoD unrevealed “Contract Data”, and “Referential Data”. 
* Legacy FPDS-NG performs User Authentication to check if the Public User ID exists with an associated Password. 
* Legacy FPDS-NG performs the Mandatory, Format, Draft or Final record and DoD revealed or unrevealed data checks, and returns the appropriate error messages.

Contract data exist in the following types:
* Award: Delivery/Task Order, Purchase Order, Definitive Contract, BPA Call
* IDV: FSS, GWAC, BOA, BPA, IDC
* NASA Specific Award: Cooperative Agreement, Funded Space Act Agreement, Grant for Research, Intragovernmental, Training Grant
* Other Transaction Award: Other Transaction Order, Other Transaction Agreement
* Other Transaction IDV: Other Transaction IDV

Sub-types of Contract Data are explained below:
* Base – The initial record that is represented as Modification Number = 0.
* Modification – The modification/amendment record to the initial record that is represented as Modification Number <> 0.


## Getting Started
FPDS-NG offers the following Contract Data Web Services to the Public Users:
1. Award
2. IDV
3. Other Transaction Award
4. Other Transaction IDV

All the Contract Data Web Services offers below API operations:
* get : Retrieves the single searched record.
* getList : Retrieves summarized results for the searched record.
* getVersion : Gets the Version for the searched record.
* exists : Checks if a searched record exists in the legacy FPDS-NG database and returns ‘true’ 
if the record exists and ‘false’ if the return does not exist. 

FPDS-NG offers the following Referential Data Web Services to the Public Users:
1. Department
2. Agency
3. Contracting Office 
4. Government Office
5. PSC 
6. NAICS 
7. System Equipment Code
8. Claimant Program Code
9. Locations
    * Countries
    * State
    * Place
    * Zip
10. Vendor

All the Referential Data Web Services offers below API operations:
* get : Retrieves the single searched record.
* getList : Retrieves summarized results for the searched record.
* exists : Checks if a searched record exists in the legacy FPDS-NG database and returns ‘true’ 
if the record exists and ‘false’ if the return does not exist. 


## API Description
### Contract Data Web Services EndPoints
**Endpoint:** https://www.fpds.gov/FPDS/BusinessServices/DataCollection/contracts/1.5/Award
<details>
<summary><b>Award get Request</b></summary>
<p>
<code><pre>
&lt;urn:get&gt;
   &lt;authenticationKey&gt;
    &lt;fpds:userID&gt;&lt;/fpds:userID&gt;
    &lt;fpds:password&gt;&lt;/fpds:password&gt;
    &lt;fpds:serviceOriginatorID&gt;&lt;/fpds:serviceOriginatorID&gt;
   &lt;/authenticationKey&gt;
   &lt;awardID&gt;
    &lt;fpds:awardContractID&gt;
     &lt;fpds:agencyID name="?" departmentID="?" departmentName="?">1900&lt;/fpds:agencyID&gt;
     &lt;fpds:PIID&gt;19AM1018P0200&lt;/fpds:PIID&gt;
     &lt;fpds:modNumber&gt;0&lt;/fpds:modNumber&gt;
    &lt;/fpds:awardContractID&gt;
   &lt;/awardID&gt;
&lt;/urn:get&gt;
</pre></code></p>
</details>

<details>
<summary><b>Award get Response</b></summary>
<p>
<code><pre>
&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;ns1:getAwardResponse xmlns:ns1="https://www.fpds.gov/FPDS"&gt;
   &lt;ns1:requestNumber&gt;1403956246&lt;/ns1:requestNumber&gt;
   &lt;ns1:confirmationNumber&gt;345057401&lt;/ns1:confirmationNumber&gt;
   &lt;ns1:outputMessages&gt;
      &lt;ns1:listOfErrors /&gt;
      &lt;ns1:listOfWarnings /&gt;
      &lt;ns1:listOfInfoMessages /&gt;
   &lt;/ns1:outputMessages&gt;
   &lt;ns1:award&gt;
      &lt;ns1:awardID&gt;
         &lt;ns1:awardContractID&gt;
            &lt;ns1:agencyID&gt;1900&lt;/ns1:agencyID&gt;
            &lt;ns1:PIID&gt;19AM1018P0200&lt;/ns1:PIID&gt;
            &lt;ns1:modNumber&gt;0&lt;/ns1:modNumber&gt;
            &lt;ns1:transactionNumber&gt;0&lt;/ns1:transactionNumber&gt;
         &lt;/ns1:awardContractID&gt;
      &lt;/ns1:awardID&gt;
      &lt;ns1:relevantContractDates&gt;
         &lt;ns1:signedDate&gt;2018-01-23 00:00:00&lt;/ns1:signedDate&gt;
         &lt;ns1:effectiveDate&gt;2018-01-23 00:00:00&lt;/ns1:effectiveDate&gt;
         &lt;ns1:currentCompletionDate&gt;2018-01-23 00:00:00&lt;/ns1:currentCompletionDate&gt;
         &lt;ns1:ultimateCompletionDate&gt;2018-01-23 00:00:00&lt;/ns1:ultimateCompletionDate&gt;
      &lt;/ns1:relevantContractDates&gt;
      &lt;ns1:dollarValues&gt;
         &lt;ns1:obligatedAmount&gt;4700.00&lt;/ns1:obligatedAmount&gt;
         &lt;ns1:baseAndExercisedOptionsValue&gt;4700.00&lt;/ns1:baseAndExercisedOptionsValue&gt;
         &lt;ns1:baseAndAllOptionsValue&gt;4700.00&lt;/ns1:baseAndAllOptionsValue&gt;
      &lt;/ns1:dollarValues&gt;
      &lt;ns1:purchaserInformation&gt;
         &lt;ns1:contractingOfficeAgencyID&gt;1900&lt;/ns1:contractingOfficeAgencyID&gt;
         &lt;ns1:contractingOfficeID&gt;19AM10&lt;/ns1:contractingOfficeID&gt;
         &lt;ns1:fundingRequestingAgencyID&gt;1900&lt;/ns1:fundingRequestingAgencyID&gt;
         &lt;ns1:fundingRequestingOfficeID&gt;19X1NL&lt;/ns1:fundingRequestingOfficeID&gt;
         &lt;ns1:foreignFunding&gt;X&lt;/ns1:foreignFunding&gt;
      &lt;/ns1:purchaserInformation&gt;
      &lt;ns1:contractMarketingData&gt;
         &lt;ns1:feePaidForUseOfService&gt;0.00&lt;/ns1:feePaidForUseOfService&gt;
      &lt;/ns1:contractMarketingData&gt;
      &lt;ns1:contractData&gt;
         &lt;ns1:contractActionType&gt;B&lt;/ns1:contractActionType&gt;
         &lt;ns1:typeOfContractPricing&gt;J&lt;/ns1:typeOfContractPricing&gt;
         &lt;ns1:nationalInterestActionCode&gt;NONE&lt;/ns1:nationalInterestActionCode&gt;
         &lt;ns1:descriptionOfContractRequirement&gt;SHIP/MSG&amp;CONS-PO-HHE,HHE/S,POV shipping for Kish and Stange&lt;/ns1:descriptionOfContractRequirement&gt;
         &lt;ns1:inherentlyGovernmentalFunction&gt;OT&lt;/ns1:inherentlyGovernmentalFunction&gt;
         &lt;ns1:GFE-GFP&gt;N&lt;/ns1:GFE-GFP&gt;
         &lt;ns1:undefinitizedAction&gt;X&lt;/ns1:undefinitizedAction&gt;
         &lt;ns1:consolidatedContract&gt;D&lt;/ns1:consolidatedContract&gt;
         &lt;ns1:performanceBasedServiceContract&gt;N&lt;/ns1:performanceBasedServiceContract&gt;
         &lt;ns1:contingencyHumanitarianPeacekeepingOperation&gt;X&lt;/ns1:contingencyHumanitarianPeacekeepingOperation&gt;
         &lt;ns1:listOfTreasuryAccounts&gt;
            &lt;ns1:treasuryAccount&gt;
               &lt;ns1:treasuryAccountSymbol&gt;
                  &lt;ns1:subLevelPrefixCode /&gt;
                  &lt;ns1:allocationTransferAgencyIdentifier /&gt;
                  &lt;ns1:agencyIdentifier&gt;19&lt;/ns1:agencyIdentifier&gt;
                  &lt;ns1:beginningPeriodOfAvailability /&gt;
                  &lt;ns1:endingPeriodOfAvailability /&gt;
                  &lt;ns1:availabilityTypeCode /&gt;
                  &lt;ns1:mainAccountCode&gt;4519&lt;/ns1:mainAccountCode&gt;
                  &lt;ns1:subAccountCode /&gt;
               &lt;/ns1:treasuryAccountSymbol&gt;
               &lt;ns1:initiative /&gt;
               &lt;ns1:obligatedAmount&gt;0&lt;/ns1:obligatedAmount&gt;
            &lt;/ns1:treasuryAccount&gt;
         &lt;/ns1:listOfTreasuryAccounts&gt;
         &lt;ns1:purchaseCardAsPaymentMethod&gt;N&lt;/ns1:purchaseCardAsPaymentMethod&gt;
         &lt;ns1:numberOfActions&gt;1&lt;/ns1:numberOfActions&gt;
      &lt;/ns1:contractData&gt;
      &lt;ns1:legislativeMandates&gt;
         &lt;ns1:ClingerCohenAct&gt;N&lt;/ns1:ClingerCohenAct&gt;
         &lt;ns1:materialsSuppliesArticlesEquipment&gt;X&lt;/ns1:materialsSuppliesArticlesEquipment&gt;
         &lt;ns1:laborStandards&gt;X&lt;/ns1:laborStandards&gt;
         &lt;ns1:constructionWageRateRequirements&gt;X&lt;/ns1:constructionWageRateRequirements&gt;
         &lt;ns1:listOfAdditionalReportingValues&gt;
            &lt;ns1:additionalReportingValue&gt;NONE&lt;/ns1:additionalReportingValue&gt;
         &lt;/ns1:listOfAdditionalReportingValues&gt;
         &lt;ns1:interagencyContractingAuthority&gt;X&lt;/ns1:interagencyContractingAuthority&gt;
      &lt;/ns1:legislativeMandates&gt;
      &lt;ns1:productOrServiceInformation&gt;
         &lt;ns1:productOrServiceCode&gt;V115&lt;/ns1:productOrServiceCode&gt;
         &lt;ns1:contractBundling&gt;H&lt;/ns1:contractBundling&gt;
         &lt;ns1:principalNAICSCode&gt;488510&lt;/ns1:principalNAICSCode&gt;
         &lt;ns1:recoveredMaterialClauses&gt;C&lt;/ns1:recoveredMaterialClauses&gt;
         &lt;ns1:manufacturingOrganizationType&gt;D&lt;/ns1:manufacturingOrganizationType&gt;
         &lt;ns1:useOfEPADesignatedProducts&gt;E&lt;/ns1:useOfEPADesignatedProducts&gt;
         &lt;ns1:countryOfOrigin&gt;ARM&lt;/ns1:countryOfOrigin&gt;
         &lt;ns1:placeOfManufacture&gt;C&lt;/ns1:placeOfManufacture&gt;
      &lt;/ns1:productOrServiceInformation&gt;
      &lt;ns1:vendor&gt;
         &lt;ns1:vendorHeader&gt;
            &lt;ns1:vendorName&gt;MISCELLANEOUS FOREIGN AWARDEES&lt;/ns1:vendorName&gt;
            &lt;ns1:vendorAlternateName&gt;FEDERAL EGOV IAE INITIATIVE - GENERIC DUNS&lt;/ns1:vendorAlternateName&gt;
            &lt;ns1:vendorLegalOrganizationName&gt;MISCELLANEOUS FOREIGN AWARDEES&lt;/ns1:vendorLegalOrganizationName&gt;
         &lt;/ns1:vendorHeader&gt;
         &lt;ns1:vendorSiteDetails&gt;
            &lt;ns1:vendorSocioEconomicIndicators&gt;
               &lt;ns1:isAlaskanNativeOwnedCorporationOrFirm&gt;false&lt;/ns1:isAlaskanNativeOwnedCorporationOrFirm&gt;
               &lt;ns1:isAmericanIndianOwned&gt;false&lt;/ns1:isAmericanIndianOwned&gt;
               &lt;ns1:isIndianTribe&gt;false&lt;/ns1:isIndianTribe&gt;
               &lt;ns1:isNativeHawaiianOwnedOrganizationOrFirm&gt;false&lt;/ns1:isNativeHawaiianOwnedOrganizationOrFirm&gt;
               &lt;ns1:isTriballyOwnedFirm&gt;false&lt;/ns1:isTriballyOwnedFirm&gt;
               &lt;ns1:isVeteranOwned&gt;false&lt;/ns1:isVeteranOwned&gt;
               &lt;ns1:isServiceRelatedDisabledVeteranOwnedBusiness&gt;false&lt;/ns1:isServiceRelatedDisabledVeteranOwnedBusiness&gt;
               &lt;ns1:isWomenOwned&gt;false&lt;/ns1:isWomenOwned&gt;
               &lt;ns1:minorityOwned&gt;
                  &lt;ns1:isMinorityOwned&gt;false&lt;/ns1:isMinorityOwned&gt;
                  &lt;ns1:isSubContinentAsianAmericanOwnedBusiness&gt;false&lt;/ns1:isSubContinentAsianAmericanOwnedBusiness&gt;
                  &lt;ns1:isAsianPacificAmericanOwnedBusiness&gt;false&lt;/ns1:isAsianPacificAmericanOwnedBusiness&gt;
                  &lt;ns1:isBlackAmericanOwnedBusiness&gt;false&lt;/ns1:isBlackAmericanOwnedBusiness&gt;
                  &lt;ns1:isHispanicAmericanOwnedBusiness&gt;false&lt;/ns1:isHispanicAmericanOwnedBusiness&gt;
                  &lt;ns1:isNativeAmericanOwnedBusiness&gt;false&lt;/ns1:isNativeAmericanOwnedBusiness&gt;
                  &lt;ns1:isOtherMinorityOwned&gt;false&lt;/ns1:isOtherMinorityOwned&gt;
               &lt;/ns1:minorityOwned&gt;
               &lt;ns1:isVerySmallBusiness&gt;false&lt;/ns1:isVerySmallBusiness&gt;
               &lt;ns1:isWomenOwnedSmallBusiness&gt;false&lt;/ns1:isWomenOwnedSmallBusiness&gt;
               &lt;ns1:isEconomicallyDisadvantagedWomenOwnedSmallBusiness&gt;false&lt;/ns1:isEconomicallyDisadvantagedWomenOwnedSmallBusiness&gt;
               &lt;ns1:isJointVentureWomenOwnedSmallBusiness&gt;false&lt;/ns1:isJointVentureWomenOwnedSmallBusiness&gt;
               &lt;ns1:isJointVentureEconomicallyDisadvantagedWomenOwnedSmallBusiness&gt;false&lt;/ns1:isJointVentureEconomicallyDisadvantagedWomenOwnedSmallBusiness&gt;
            &lt;/ns1:vendorSocioEconomicIndicators&gt;
            &lt;ns1:vendorBusinessTypes&gt;
               &lt;ns1:isCommunityDevelopedCorporationOwnedFirm&gt;false&lt;/ns1:isCommunityDevelopedCorporationOwnedFirm&gt;
               &lt;ns1:isLaborSurplusAreaFirm&gt;false&lt;/ns1:isLaborSurplusAreaFirm&gt;
               &lt;ns1:federalGovernment&gt;
                  &lt;ns1:isFederalGovernment&gt;false&lt;/ns1:isFederalGovernment&gt;
                  &lt;ns1:isFederallyFundedResearchAndDevelopmentCorp&gt;false&lt;/ns1:isFederallyFundedResearchAndDevelopmentCorp&gt;
                  &lt;ns1:isFederalGovernmentAgency&gt;false&lt;/ns1:isFederalGovernmentAgency&gt;
               &lt;/ns1:federalGovernment&gt;
               &lt;ns1:isStateGovernment&gt;false&lt;/ns1:isStateGovernment&gt;
               &lt;ns1:localGovernment&gt;
                  &lt;ns1:isLocalGovernment&gt;false&lt;/ns1:isLocalGovernment&gt;
                  &lt;ns1:isCityLocalGovernment&gt;false&lt;/ns1:isCityLocalGovernment&gt;
                  &lt;ns1:isCountyLocalGovernment&gt;false&lt;/ns1:isCountyLocalGovernment&gt;
                  &lt;ns1:isInterMunicipalLocalGovernment&gt;false&lt;/ns1:isInterMunicipalLocalGovernment&gt;
                  &lt;ns1:isLocalGovernmentOwned&gt;false&lt;/ns1:isLocalGovernmentOwned&gt;
                  &lt;ns1:isMunicipalityLocalGovernment&gt;false&lt;/ns1:isMunicipalityLocalGovernment&gt;
                  &lt;ns1:isSchoolDistrictLocalGovernment&gt;false&lt;/ns1:isSchoolDistrictLocalGovernment&gt;
                  &lt;ns1:isTownshipLocalGovernment&gt;false&lt;/ns1:isTownshipLocalGovernment&gt;
               &lt;/ns1:localGovernment&gt;
               &lt;ns1:isTribalGovernment&gt;false&lt;/ns1:isTribalGovernment&gt;
               &lt;ns1:isForeignGovernment&gt;false&lt;/ns1:isForeignGovernment&gt;
               &lt;ns1:businessOrOrganizationType&gt;
                  &lt;ns1:isCorporateEntityNotTaxExempt&gt;false&lt;/ns1:isCorporateEntityNotTaxExempt&gt;
                  &lt;ns1:isCorporateEntityTaxExempt&gt;false&lt;/ns1:isCorporateEntityTaxExempt&gt;
                  &lt;ns1:isPartnershipOrLimitedLiabilityPartnership&gt;false&lt;/ns1:isPartnershipOrLimitedLiabilityPartnership&gt;
                  &lt;ns1:isSolePropreitorship&gt;false&lt;/ns1:isSolePropreitorship&gt;
                  &lt;ns1:isSmallAgriculturalCooperative&gt;false&lt;/ns1:isSmallAgriculturalCooperative&gt;
                  &lt;ns1:isInternationalOrganization&gt;false&lt;/ns1:isInternationalOrganization&gt;
               &lt;/ns1:businessOrOrganizationType&gt;
            &lt;/ns1:vendorBusinessTypes&gt;
            &lt;ns1:vendorLineOfBusiness&gt;
               &lt;ns1:isCommunityDevelopmentCorporation&gt;false&lt;/ns1:isCommunityDevelopmentCorporation&gt;
               &lt;ns1:isDomesticShelter&gt;false&lt;/ns1:isDomesticShelter&gt;
               &lt;ns1:isEducationalInstitution&gt;false&lt;/ns1:isEducationalInstitution&gt;
               &lt;ns1:isFoundation&gt;false&lt;/ns1:isFoundation&gt;
               &lt;ns1:isHospital&gt;false&lt;/ns1:isHospital&gt;
               &lt;ns1:isManufacturerOfGoods&gt;false&lt;/ns1:isManufacturerOfGoods&gt;
               &lt;ns1:isVeterinaryHospital&gt;false&lt;/ns1:isVeterinaryHospital&gt;
               &lt;ns1:isHispanicServicingInstitution&gt;false&lt;/ns1:isHispanicServicingInstitution&gt;
            &lt;/ns1:vendorLineOfBusiness&gt;
            &lt;ns1:vendorRelationshipWithFederalGovernment&gt;
               &lt;ns1:receivesContracts&gt;false&lt;/ns1:receivesContracts&gt;
               &lt;ns1:receivesGrants&gt;false&lt;/ns1:receivesGrants&gt;
               &lt;ns1:receivesContractsAndGrants&gt;true&lt;/ns1:receivesContractsAndGrants&gt;
            &lt;/ns1:vendorRelationshipWithFederalGovernment&gt;
            &lt;ns1:typeOfGovernmentEntity&gt;
               &lt;ns1:isAirportAuthority&gt;false&lt;/ns1:isAirportAuthority&gt;
               &lt;ns1:isCouncilOfGovernments&gt;false&lt;/ns1:isCouncilOfGovernments&gt;
               &lt;ns1:isHousingAuthoritiesPublicOrTribal&gt;false&lt;/ns1:isHousingAuthoritiesPublicOrTribal&gt;
               &lt;ns1:isInterstateEntity&gt;false&lt;/ns1:isInterstateEntity&gt;
               &lt;ns1:isPlanningCommission&gt;false&lt;/ns1:isPlanningCommission&gt;
               &lt;ns1:isPortAuthority&gt;false&lt;/ns1:isPortAuthority&gt;
               &lt;ns1:isTransitAuthority&gt;false&lt;/ns1:isTransitAuthority&gt;
            &lt;/ns1:typeOfGovernmentEntity&gt;
            &lt;ns1:vendorOrganizationFactors&gt;
               &lt;ns1:isSubchapterSCorporation&gt;false&lt;/ns1:isSubchapterSCorporation&gt;
               &lt;ns1:isLimitedLiabilityCorporation&gt;false&lt;/ns1:isLimitedLiabilityCorporation&gt;
               &lt;ns1:isForeignOwnedAndLocated&gt;false&lt;/ns1:isForeignOwnedAndLocated&gt;
               &lt;ns1:profitStructure&gt;
                  &lt;ns1:isForProfitOrganization&gt;true&lt;/ns1:isForProfitOrganization&gt;
                  &lt;ns1:isNonprofitOrganization&gt;false&lt;/ns1:isNonprofitOrganization&gt;
                  &lt;ns1:isOtherNotForProfitOrganization&gt;false&lt;/ns1:isOtherNotForProfitOrganization&gt;
               &lt;/ns1:profitStructure&gt;
               &lt;ns1:isShelteredWorkshop&gt;false&lt;/ns1:isShelteredWorkshop&gt;
               &lt;ns1:stateOfIncorporation&gt;DC&lt;/ns1:stateOfIncorporation&gt;
               &lt;ns1:countryOfIncorporation&gt;USA&lt;/ns1:countryOfIncorporation&gt;
               &lt;ns1:organizationalType&gt;OTHER&lt;/ns1:organizationalType&gt;
            &lt;/ns1:vendorOrganizationFactors&gt;
            &lt;ns1:typeOfEducationalEntity&gt;
               &lt;ns1:is1862LandGrantCollege&gt;false&lt;/ns1:is1862LandGrantCollege&gt;
               &lt;ns1:is1890LandGrantCollege&gt;false&lt;/ns1:is1890LandGrantCollege&gt;
               &lt;ns1:is1994LandGrantCollege&gt;false&lt;/ns1:is1994LandGrantCollege&gt;
               &lt;ns1:isHistoricallyBlackCollegeOrUniversity&gt;false&lt;/ns1:isHistoricallyBlackCollegeOrUniversity&gt;
               &lt;ns1:isMinorityInstitution&gt;false&lt;/ns1:isMinorityInstitution&gt;
               &lt;ns1:isPrivateUniversityOrCollege&gt;false&lt;/ns1:isPrivateUniversityOrCollege&gt;
               &lt;ns1:isSchoolOfForestry&gt;false&lt;/ns1:isSchoolOfForestry&gt;
               &lt;ns1:isStateControlledInstitutionofHigherLearning&gt;false&lt;/ns1:isStateControlledInstitutionofHigherLearning&gt;
               &lt;ns1:isTribalCollege&gt;false&lt;/ns1:isTribalCollege&gt;
               &lt;ns1:isVeterinaryCollege&gt;false&lt;/ns1:isVeterinaryCollege&gt;
            &lt;/ns1:typeOfEducationalEntity&gt;
            &lt;ns1:vendorCertifications&gt;
               &lt;ns1:isDOTCertifiedDisadvantagedBusinessEnterprise&gt;false&lt;/ns1:isDOTCertifiedDisadvantagedBusinessEnterprise&gt;
               &lt;ns1:isSelfCertifiedSmallDisadvantagedBusiness&gt;false&lt;/ns1:isSelfCertifiedSmallDisadvantagedBusiness&gt;
               &lt;ns1:isSBACertifiedSmallDisadvantagedBusiness&gt;false&lt;/ns1:isSBACertifiedSmallDisadvantagedBusiness&gt;
               &lt;ns1:isSBACertified8AProgramParticipant&gt;false&lt;/ns1:isSBACertified8AProgramParticipant&gt;
               &lt;ns1:isSelfCertifiedHUBZoneJointVenture&gt;false&lt;/ns1:isSelfCertifiedHUBZoneJointVenture&gt;
               &lt;ns1:isSBACertifiedHUBZone&gt;false&lt;/ns1:isSBACertifiedHUBZone&gt;
               &lt;ns1:isSBACertified8AJointVenture&gt;false&lt;/ns1:isSBACertified8AJointVenture&gt;
            &lt;/ns1:vendorCertifications&gt;
            &lt;ns1:vendorLocation&gt;
               &lt;ns1:streetAddress&gt;1800 F ST NW&lt;/ns1:streetAddress&gt;
               &lt;ns1:city&gt;WASHINGTON&lt;/ns1:city&gt;
               &lt;ns1:state&gt;DC&lt;/ns1:state&gt;
               &lt;ns1:ZIPCode&gt;204050001&lt;/ns1:ZIPCode&gt;
               &lt;ns1:countryCode&gt;USA&lt;/ns1:countryCode&gt;
               &lt;ns1:phoneNo&gt;2022159767&lt;/ns1:phoneNo&gt;
               &lt;ns1:congressionalDistrictCode&gt;00&lt;/ns1:congressionalDistrictCode&gt;
            &lt;/ns1:vendorLocation&gt;
            &lt;ns1:vendorSiteCode&gt;123456787&lt;/ns1:vendorSiteCode&gt;
            &lt;ns1:vendorAlternateSiteCode&gt;20405&lt;/ns1:vendorAlternateSiteCode&gt;
            &lt;ns1:vendorDUNSInformation&gt;
               &lt;ns1:DUNSNumber&gt;123456787&lt;/ns1:DUNSNumber&gt;
               &lt;ns1:cageCode&gt;35KC0&lt;/ns1:cageCode&gt;
            &lt;/ns1:vendorDUNSInformation&gt;
            &lt;ns1:ccrRegistrationDetails&gt;
               &lt;ns1:registrationDate&gt;2005-01-20 00:00:00&lt;/ns1:registrationDate&gt;
               &lt;ns1:renewalDate&gt;2018-03-29 00:00:00&lt;/ns1:renewalDate&gt;
            &lt;/ns1:ccrRegistrationDetails&gt;
         &lt;/ns1:vendorSiteDetails&gt;
         &lt;ns1:contractingOfficerBusinessSizeDetermination&gt;O&lt;/ns1:contractingOfficerBusinessSizeDetermination&gt;
      &lt;/ns1:vendor&gt;
      &lt;ns1:placeOfPerformance&gt;
         &lt;ns1:principalPlaceOfPerformance&gt;
            &lt;ns1:countryCode&gt;ARM&lt;/ns1:countryCode&gt;
         &lt;/ns1:principalPlaceOfPerformance&gt;
      &lt;/ns1:placeOfPerformance&gt;
      &lt;ns1:competition&gt;
         &lt;ns1:extentCompeted&gt;F&lt;/ns1:extentCompeted&gt;
         &lt;ns1:solicitationProcedures&gt;SP1&lt;/ns1:solicitationProcedures&gt;
         &lt;ns1:typeOfSetAside&gt;NONE&lt;/ns1:typeOfSetAside&gt;
         &lt;ns1:typeOfSetAsideSource&gt;F&lt;/ns1:typeOfSetAsideSource&gt;
         &lt;ns1:evaluatedPreference&gt;NONE&lt;/ns1:evaluatedPreference&gt;
         &lt;ns1:numberOfOffersReceived&gt;3&lt;/ns1:numberOfOffersReceived&gt;
         &lt;ns1:numberOfOffersSource&gt;F&lt;/ns1:numberOfOffersSource&gt;
         &lt;ns1:commercialItemAcquisitionProcedures&gt;B&lt;/ns1:commercialItemAcquisitionProcedures&gt;
         &lt;ns1:commercialItemTestProgram&gt;N&lt;/ns1:commercialItemTestProgram&gt;
         &lt;ns1:A76Action&gt;N&lt;/ns1:A76Action&gt;
         &lt;ns1:fedBizOpps&gt;X&lt;/ns1:fedBizOpps&gt;
         &lt;ns1:localAreaSetAside&gt;N&lt;/ns1:localAreaSetAside&gt;
      &lt;/ns1:competition&gt;
      &lt;ns1:preferencePrograms&gt;
         &lt;ns1:subcontractPlan&gt;B&lt;/ns1:subcontractPlan&gt;
      &lt;/ns1:preferencePrograms&gt;
      &lt;ns1:transactionInformation&gt;
         &lt;ns1:createdBy&gt;ARAKELYANT&lt;/ns1:createdBy&gt;
         &lt;ns1:createdDate&gt;2018-01-23 04:47:24&lt;/ns1:createdDate&gt;
         &lt;ns1:lastModifiedBy&gt;ARAKELYANT&lt;/ns1:lastModifiedBy&gt;
         &lt;ns1:lastModifiedDate&gt;2018-01-23 08:06:21&lt;/ns1:lastModifiedDate&gt;
         &lt;ns1:closedStatus&gt;N&lt;/ns1:closedStatus&gt;
         &lt;ns1:status&gt;F&lt;/ns1:status&gt;
      &lt;/ns1:transactionInformation&gt;
      &lt;ns1:genericTags&gt;
         &lt;ns1:genericStrings /&gt;
      &lt;/ns1:genericTags&gt;
   &lt;/ns1:award&gt;
&lt;/ns1:getAwardResponse&gt;
</pre></code></p>
</details>

**Endpoint:** https://www.fpds.gov/FPDS/BusinessServices/DataCollection/contracts/1.5/IDV
<details>
<summary><b>IDV getList  Request</b></summary>
<p>
<code><pre>
&lt;urn:getList&gt;
    &lt;authenticationKey&gt;
     &lt;fpds:userID&gt;&lt;/fpds:userID&gt;
     &lt;fpds:password&gt;&lt;/fpds:password&gt;
     &lt;fpds:serviceOriginatorID&gt;&lt;/fpds:serviceOriginatorID&gt;
    &lt;/authenticationKey&gt;
    &lt;IDVSearchCriteria&gt;
     &lt;fpds:agencyID name="?" departmentID="?" departmentName="?"&gt;1900&lt;/fpds:agencyID&gt;
     &lt;fpds:PIID&gt;SAF20010A5103&lt;/fpds:PIID&gt;
     &lt;fpds:signedDateFrom&gt;2010-10-01 00:00:00&lt;/fpds:signedDateFrom&gt;
     &lt;fpds:signedDateTo&gt;2010-10-01 00:00:00&lt;/fpds:signedDateTo&gt;
    &lt;/IDVSearchCriteria&gt;
&lt;/urn:getList&gt; 
</pre></code></p>
</details>

<details>
<summary><b>IDV getList Response</b></summary>
<p>
<code><pre>
&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;ns1:getListIDVResponse xmlns:ns1="https://www.fpds.gov/FPDS"&gt;
   &lt;ns1:requestNumber&gt;1429249984&lt;/ns1:requestNumber&gt;
   &lt;ns1:confirmationNumber&gt;379252480&lt;/ns1:confirmationNumber&gt;
   &lt;ns1:outputMessages&gt;
      &lt;ns1:listOfErrors /&gt;
      &lt;ns1:listOfWarnings /&gt;
      &lt;ns1:listOfInfoMessages /&gt;
   &lt;/ns1:outputMessages&gt;
   &lt;ns1:listOfIDVSummaries&gt;
      &lt;ns1:count&gt;
         &lt;ns1:total&gt;1&lt;/ns1:total&gt;
         &lt;ns1:fetched&gt;1&lt;/ns1:fetched&gt;
      &lt;/ns1:count&gt;
      &lt;ns1:IDVSummary&gt;
         &lt;ns1:contractID&gt;
            &lt;ns1:IDVID&gt;
               &lt;ns1:agencyID&gt;1900&lt;/ns1:agencyID&gt;
               &lt;ns1:PIID&gt;SAF20010A5103&lt;/ns1:PIID&gt;
               &lt;ns1:modNumber&gt;0&lt;/ns1:modNumber&gt;
            &lt;/ns1:IDVID&gt;
         &lt;/ns1:contractID&gt;
         &lt;ns1:listOfOtherIDsForThisIDV /&gt;
         &lt;ns1:contractActionType&gt;E&lt;/ns1:contractActionType&gt;
         &lt;ns1:agencyName&gt;STATE, DEPARTMENT OF&lt;/ns1:agencyName&gt;
         &lt;ns1:officeName&gt;AMERICAN EMBASSY - KABUL&lt;/ns1:officeName&gt;
         &lt;ns1:vendorName&gt;MISCELLANEOUS FOREIGN CONTRACTORS&lt;/ns1:vendorName&gt;
         &lt;ns1:NAICSCode&gt;336312&lt;/ns1:NAICSCode&gt;
         &lt;ns1:signedDate&gt;2010-10-01 00:00:00&lt;/ns1:signedDate&gt;
         &lt;ns1:obligatedAmount&gt;100000.00&lt;/ns1:obligatedAmount&gt;
         &lt;ns1:baseAndAllOptionsValue&gt;100000.00&lt;/ns1:baseAndAllOptionsValue&gt;
         &lt;ns1:transactionInformation&gt;
            &lt;ns1:createdBy&gt;NOORAW&lt;/ns1:createdBy&gt;
            &lt;ns1:createdDate&gt;2011-07-12 04:08:45&lt;/ns1:createdDate&gt;
            &lt;ns1:lastModifiedBy&gt;NOORAW&lt;/ns1:lastModifiedBy&gt;
            &lt;ns1:lastModifiedDate&gt;2011-07-12 04:09:01&lt;/ns1:lastModifiedDate&gt;
            &lt;ns1:status&gt;F&lt;/ns1:status&gt;
            &lt;ns1:transactionSource&gt;CREATE:WP,UPDATE:WP&lt;/ns1:transactionSource&gt;
         &lt;/ns1:transactionInformation&gt;
         &lt;ns1:version&gt;1.4&lt;/ns1:version&gt;
      &lt;/ns1:IDVSummary&gt;
   &lt;/ns1:listOfIDVSummaries&gt;
&lt;/ns1:getListIDVResponse&gt;
</pre></code></p>
</details>


**Endpoint:** https://www.fpds.gov/FPDS/BusinessServices/DataCollection/contracts/1.5/OtherTransactionAward
<details>
<summary><b>Other Transaction Award getVersion Request</b></summary>
<p>
<code><pre>
&lt;urn:getVersion&gt;
    &lt;authenticationKey&gt;
     &lt;fpds:userID&gt;&lt;/fpds:userID&gt;
     &lt;fpds:password&gt;&lt;/fpds:password&gt;
     &lt;fpds:serviceOriginatorID&gt;&lt;/fpds:serviceOriginatorID&gt;
    &lt;/authenticationKey&gt;
     &lt;OtherTransactionAwardID&gt;
      &lt;fpds:OtherTransactionAwardContractID&gt;
      &lt;fpds:agencyID name="?" departmentID="?" departmentName="?"&gt;9700&lt;/fpds:agencyID&gt;
      &lt;fpds:PIID&gt;0001&lt;/fpds:PIID&gt;
      &lt;fpds:modNumber&gt;0&lt;/fpds:modNumber&gt;
     &lt;/fpds:OtherTransactionAwardContractID&gt;
     &lt;fpds:referencedIDVID&gt;
      &lt;fpds:agencyID name="?" departmentID="?" departmentName="?"&gt;9700&lt;/fpds:agencyID&gt;
      &lt;fpds:PIID&gt;W81XWH1590001&lt;/fpds:PIID&gt;
      &lt;fpds:modNumber&gt;0&lt;/fpds:modNumber&gt;
     &lt;/fpds:referencedIDVID&gt;
    &lt;/OtherTransactionAwardID&gt;
&lt;/urn:getVersion&gt;
</pre></code></p>
</details>

<details>
<summary><b>Other Transaction Award getVersion Response</b></summary>
<p>
<code><pre>
&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;ns1:getVersionOtherTransactionAwardResponse xmlns:ns1="https://www.fpds.gov/FPDS"&gt;
   &lt;ns1:requestNumber&gt;1430163809&lt;/ns1:requestNumber&gt;
   &lt;ns1:confirmationNumber&gt;381782910&lt;/ns1:confirmationNumber&gt;
   &lt;ns1:outputMessages&gt;
      &lt;ns1:listOfErrors /&gt;
      &lt;ns1:listOfWarnings /&gt;
      &lt;ns1:listOfInfoMessages /&gt;
   &lt;/ns1:outputMessages&gt;
   &lt;ns1:versionNumber&gt;1.4&lt;/ns1:versionNumber&gt;
&lt;/ns1:getVersionOtherTransactionAwardResponse&gt;
</pre></code></p>
</details>


**Endpoint:** https://www.fpds.gov/FPDS/BusinessServices/DataCollection/contracts/1.5/OtherTransactionIDV
<details>
<summary><b>Other Transaction IDV exists  Request</b></summary>
<p>
<code><pre>
&lt;urn:exists&gt;
    &lt;authenticationKey&gt;
     &lt;fpds:userID&gt;&lt;/fpds:userID&gt;
     &lt;fpds:password&gt;&lt;/fpds:password&gt;
     &lt;fpds:serviceOriginatorID&gt;&lt;/fpds:serviceOriginatorID&gt;
    &lt;/authenticationKey&gt;
    &lt;OtherTransactionIDVID&gt;
     &lt;fpds:OtherTransactionIDVContractID&gt;
     &lt;fpds:agencyID name="?" departmentID="?" departmentName="?"&gt;7000&lt;/fpds:agencyID&gt;
     &lt;fpds:PIID&gt;9999&lt;/fpds:PIID&gt;
     &lt;fpds:modNumber&gt;0&lt;/fpds:modNumber&gt;
     &lt;/fpds:OtherTransactionIDVContractID&gt;
    &lt;/OtherTransactionIDVID&gt;
&lt;/urn:exists&gt;
</pre></code></p>
</details>

<details>
<summary><b>Other Transaction IDV exists Response</b></summary>
<p>
<code><pre>
&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;ns1:existsOtherTransactionIDVResponse xmlns:ns1="https://www.fpds.gov/FPDS"&gt;
   &lt;ns1:requestNumber&gt;1429863775&lt;/ns1:requestNumber&gt;
   &lt;ns1:confirmationNumber&gt;381392724&lt;/ns1:confirmationNumber&gt;
   &lt;ns1:outputMessages&gt;
      &lt;ns1:listOfErrors /&gt;
      &lt;ns1:listOfWarnings /&gt;
      &lt;ns1:listOfInfoMessages /&gt;
   &lt;/ns1:outputMessages&gt;
   &lt;ns1:isExists&gt;false&lt;/ns1:isExists&gt;
&lt;/ns1:existsOtherTransactionIDVResponse&gt;
</pre></code></p>
</details>


### Referential Data Web Services EndPoints
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/ServiceClassifications/1.0/PSC 
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/ServiceClassifications/1.0/NAICS
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/ServiceClassifications/1.0/ClaimantProgramCode 
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/ServiceClassifications/1.0/SystemEquipmentCode
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/locations/1.0/Country 
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/locations/1.0/State 
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/locations/1.0/Place 
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/locations/1.0/ZIP
https://www.fpds.gov/OrganizationalHierarchy/BusinessServices/Organization/1.0/Organization
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/organizations/1.0/Department
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/organizations/1.0/Agency
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/organizations/1.0/ContractingOffice
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/organizations/1.2/GovernmentOffice
https://www.fpds.gov/FPDS/BusinessServices/DataCollection/vendors/1.0/Vendor


**Endpoint:** https://www.fpds.gov/FPDS/BusinessServices/DataCollection/vendors/1.0/Vendor
<details>
<summary><b>Vendor getList  Request</b></summary>
<p>
<code><pre>
&lt;urn:getList&gt;
    &lt;authenticationKey&gt;
     &lt;fpds:userID&gt;&lt;/fpds:userID&gt;
     &lt;fpds:password&gt;&lt;/fpds:password&gt;
     &lt;fpds:serviceOriginatorID&gt;&lt;/fpds:serviceOriginatorID&gt;
    &lt;/authenticationKey&gt;
    &lt;vendorSearchCriteria&gt;
     &lt;fpds:DUNSNumber&gt;123456787&lt;/fpds:DUNSNumber&gt;            
    &lt;/vendorSearchCriteria&gt;
&lt;/urn:getList&gt;
</pre></code></p>
</details>

<details>
<summary><b>Vendor getList Response</b></summary>
<p>
<code><pre>
&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;ns1:getListVendorResponse xmlns:ns1="https://www.fpds.gov/FPDS"&gt;
   &lt;ns1:requestNumber&gt;1430801638&lt;/ns1:requestNumber&gt;
   &lt;ns1:confirmationNumber&gt;382471106&lt;/ns1:confirmationNumber&gt;
   &lt;ns1:outputMessages&gt;
      &lt;ns1:listOfErrors /&gt;
      &lt;ns1:listOfWarnings /&gt;
      &lt;ns1:listOfInfoMessages /&gt;
   &lt;/ns1:outputMessages&gt;
   &lt;ns1:listOfVendors&gt;
      &lt;ns1:count&gt;
         &lt;ns1:total&gt;1&lt;/ns1:total&gt;
         &lt;ns1:fetched&gt;1&lt;/ns1:fetched&gt;
      &lt;/ns1:count&gt;
      &lt;ns1:vendor&gt;
         &lt;ns1:vendorHeader&gt;
            &lt;ns1:vendorName&gt;MISCELLANEOUS FOREIGN AWARDEES&lt;/ns1:vendorName&gt;
            &lt;ns1:vendorDoingAsBusinessName&gt;FEDERAL EGOV IAE INITIATIVE - GENERIC DUNS&lt;/ns1:vendorDoingAsBusinessName&gt;
         &lt;/ns1:vendorHeader&gt;
         &lt;ns1:listOfVendorSiteDetails&gt;
            &lt;ns1:vendorSiteDetails&gt;
               &lt;ns1:vendorSocioEconomicIndicators /&gt;
               &lt;ns1:vendorLocation&gt;
                  &lt;ns1:streetAddress&gt;1800 F ST NW&lt;/ns1:streetAddress&gt;
                  &lt;ns1:city&gt;WASHINGTON&lt;/ns1:city&gt;
                  &lt;ns1:state&gt;DC&lt;/ns1:state&gt;
                  &lt;ns1:ZIPCode&gt;204050001&lt;/ns1:ZIPCode&gt;
                  &lt;ns1:countryCode&gt;USA&lt;/ns1:countryCode&gt;
                  &lt;ns1:phoneNo&gt;2022159767&lt;/ns1:phoneNo&gt;
                  &lt;ns1:faxNo /&gt;
               &lt;/ns1:vendorLocation&gt;
               &lt;ns1:vendorDUNSInformation&gt;
                  &lt;ns1:DUNSNumber&gt;123456787&lt;/ns1:DUNSNumber&gt;
                  &lt;ns1:cageCode&gt;35KC0&lt;/ns1:cageCode&gt;
               &lt;/ns1:vendorDUNSInformation&gt;
            &lt;/ns1:vendorSiteDetails&gt;
         &lt;/ns1:listOfVendorSiteDetails&gt;
      &lt;/ns1:vendor&gt;
   &lt;/ns1:listOfVendors&gt;
&lt;/ns1:getListVendorResponse&gt;
</pre></code></p>
</details>

**Endpoint:** https://www.fpds.gov/FPDS/BusinessServices/DataCollection/ServiceClassifications/1.0/SystemEquipmentCode
<details>
<summary><b>System Equipment Code exists  Request</b></summary>
<p>
<code><pre>
&lt;urn:exists&gt;
    &lt;authenticationKey&gt;
     &lt;fpds:userID&gt;&lt;/fpds:userID&gt;
     &lt;fpds:password&gt;&lt;/fpds:password&gt;
     &lt;fpds:serviceOriginatorID&gt;&lt;/fpds:serviceOriginatorID&gt;
    &lt;/authenticationKey&gt;
    &lt;systemEquipmentCode&gt;000&lt;/systemEquipmentCode&gt;
&lt;/urn:exists&gt;
</pre></code></p>
</details>
 
<details>
<summary><b>System Equipment Code exists Response</b></summary>
<p>
<code><pre>
&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;ns1:existsSystemEquipmentResponse xmlns:ns1="https://www.fpds.gov/FPDS"&gt;
   &lt;ns1:requestNumber&gt;1430802219&lt;/ns1:requestNumber&gt;
   &lt;ns1:confirmationNumber&gt;382471543&lt;/ns1:confirmationNumber&gt;
   &lt;ns1:outputMessages&gt;
      &lt;ns1:listOfErrors /&gt;
      &lt;ns1:listOfWarnings /&gt;
      &lt;ns1:listOfInfoMessages /&gt;
   &lt;/ns1:outputMessages&gt;
   &lt;ns1:isExists&gt;true&lt;/ns1:isExists&gt;
&lt;/ns1:existsSystemEquipmentResponse&gt;
</pre></code></p>
</details>

**Endpoint:** https://www.fpds.gov/FPDS/BusinessServices/DataCollection/organizations/1.0/Department
<details>
<summary><b>Department get Request</b></summary>
<p>
<code><pre>
&lt;urn:get&gt;
   &lt;authenticationKey&gt;
    &lt;fpds:userID&gt;&lt;/fpds:userID&gt;
    &lt;fpds:password&gt;&lt;/fpds:password&gt;
    &lt;fpds:serviceOriginatorID&gt;&lt;/fpds:serviceOriginatorID&gt;
   &lt;/authenticationKey&gt;
   &lt;departmentID&gt;9700&lt;/departmentID&gt;
&lt;/urn:get&gt; 
</pre></code></p>
</details>

<details>
<summary><b>Department get Response</b></summary>
<p>
<code><pre>
&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;ns1:getDepartmentResponse xmlns:ns1="https://www.fpds.gov/FPDS"&gt;
   &lt;ns1:requestNumber&gt;1430803539&lt;/ns1:requestNumber&gt;
   &lt;ns1:confirmationNumber&gt;382472539&lt;/ns1:confirmationNumber&gt;
   &lt;ns1:outputMessages&gt;
      &lt;ns1:listOfErrors /&gt;
      &lt;ns1:listOfWarnings /&gt;
      &lt;ns1:listOfInfoMessages /&gt;
   &lt;/ns1:outputMessages&gt;
   &lt;ns1:department&gt;
      &lt;ns1:departmentID&gt;9700&lt;/ns1:departmentID&gt;
      &lt;ns1:departmentName&gt;DEPT OF DEFENSE&lt;/ns1:departmentName&gt;
   &lt;/ns1:department&gt;
&lt;/ns1:getDepartmentResponse&gt;
</pre></code></p>
</details>


## OpenAPI Specification File 

## HTTP Response Codes

| HTTP Response Code | Description |
| ---- | ----------- |
| 200 | Successful. Data will be returned in JSON format. |
| 400 | Application Level Error Messages:  |
| 403 | API key is not correct or was not provided. |


## Contact Us