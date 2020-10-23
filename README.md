// import com.fasterxml.jackson.databind.ObjectMapper; // version 2.11.1
// import com.fasterxml.jackson.annotation.JsonProperty; // version 2.11.1
/* ObjectMapper om = new ObjectMapper();
Root root = om.readValue(myJsonString), Root.class); */
public class BlacklistAndNegativelistDetails{
    public Object blacklistNotes;
    public List<Object> blacklistCode;
    public Object blacklistReasonCode;
    public Object blacklistStatusCode;
    public Object negationStatusCode;
    public Object negationNotes;
    public Object negationReasonCode;
    public List<Object> negationReason;
}

public class Address{
    public Object addressStartDate;
    public Object addressEndDate;
    public String addressLine1;
    public String addressLine2;
    public Object addressLine3;
    public Object addressLine4;
    public Object addressLine5;
    public Object addressLine6;
    public String addressTypeIndicator;
    public String addressIndicator;
    public String buildingNumber;
    public String buildingLevel;
    public Object city;
    public Object country;
    public String countryCode;
    public Object domicile;
    public Object freeTextAddress;
    public Object freeTextLabel;
    public Object holdMailFlag;
    public Object holdMailReason;
    public String houseNumber;
    public Object localityName;
    public String postalCode;
    public Object preferredAddressIndicator;
    public Object premiseName;
    public Object state;
    public Object streetName;
    public Object streetNumber;
    public Object suburban;
    public Object town;
}

public class DemographicInfo{
    public Object incomeFrom;
    public Object incomeTo;
    public Object netWorth;
    public Object sourceOfIncome;
    public Object cityOfResidence;
    public Object annualSalary;
}

public class SegmentLevelsAndNumber{
    public String segmentationLevel;
    public String segmentationType;
    public String segmentTypeAndLevel;
    public int segmentationNumber;
    public String segmentationNumberDescription;
}

public class GeneralInfo{
    public Object nameInNativeLanguage;
    public Object alternateFullName;
    public Object baseCurrency;
    public Object branchId;
    public Object residingCity;
    public String customerTypeCode;
    public Object nickName;
    public Object statusCode;
    public String customerStatus1;
    public String customerStatusDescription1;
    public String customerStatus2;
    public Object customerStatusDescription2;
    public String customerStatus3;
    public Object customerStatusDescription3;
    public String customerStatus4;
    public Object customerStatusDescription4;
    public Object entityTypeAndEntityDoc;
    public Object holdMailInitiatedBy;
    public boolean staffIndicatorFlag;
    public String staffIndicator;
    public Object suspensionStatusCode;
    public Object languageCode;
    public Object lastUpdatedDate;
    public Object otpNumberLastUpdatedDate;
    public Object preferredName;
    public Object recordStatus;
    public Object salutationCode;
    public Object primaryRelationshipManagerId;
    public Object secondaryRelationshipManagerId;
    public Object tertiaryRelationshipManagerId;
    public String segmentCode;
    public String segmentCodeDescription;
    public Object subSegmentCode;
    public Object subSegmentCodeDescription;
    public List<SegmentLevelsAndNumber> segmentLevelsAndNumber;
    public Object segmentLevel;
    public Object segmentNumber;
    public Object customerCategoryCode;
    public Object customerCategoryCodeDescription;
    public Object shortName;
    public Object staffId;
    public Object residingState;
    public Object suspensionNotes;
    public List<Object> suspensionInfo;
    public Object suspensionReasonCode;
    public Object maidenName;
    public Object spouseName;
    public Object fatherName;
    public Object motherMaidenName;
    public Object subSegment;
    public Object suspensionStartDate;
    public Object ebankingEnabledFlag;
    public Object ebankingEnabled;
    public Object customerLanguage;
    public String sourceCustomerSuffix;
    public String systemCustomerSuffix;
}

public class ExtendedGeneralInfo{
    public Object customerRiskRating;
    public Object ratingCode;
    public Object riskProfileExpiryDate;
    public Object customerOwner;
    public Object taxStatus;
    public Object riskScoreDate;
    public Object riskScore;
    public Object riskCategoryCode;
    public Object dateOfBecomingNRE;
    public Object riskEffectiveDate;
    public Object politicallyExposed;
    public Object gstFlag;
    public Object groupIdCode;
}

public class CorporateCustomerInfo{
    public Object corporateName;
    public Object alternateShortName;
    public Object assignedPriority;
    public Object businessType;
    public Object cityOfIncorporation;
    public Object corporateAlternateName;
    public Object entityType;
    public Object incorporationDate;
    public Object languageDescription;
    public Object legalEntityType;
    public Object masIndustry;
    public Object otherRelationship;
    public Object principalNatureOfBusiness;
    public Object principalPlaceOfOperation;
    public Object relationshipSubType;
    public Object sicCode;
    public Object pbCategory;
    public Object industry;
    public Object constitutionCode;
    public List<Object> constitutionCodeDescription;
    public Object cbcIndustry;
    public Object jcicIndustry;
    public Object region;
    public Object businessCentre;
    public Object directSaleAgentId;
}

public class NationalityCodeDescription{
    public String customerNationalityDescription;
    public String languageCode;
}

public class RetailCustomerInfo{
    public String firstName;
    public Object middleName;
    public Object lastName;
    public Object additionalName;
    public long dateOfBirth;
    public String genderCode;
    public Object maritalStatusCode;
    public List<Object> maritalStatusCodeDescription;
    public Object maritalStatusDescription;
    public String nationalityCode;
    public List<NationalityCodeDescription> nationalityCodeDescription;
    public Object nationalityDescription;
    public Object optOutIndicator;
    public Object race;
    public Object raceDescription;
    public Object taxDeductedSource;
    public Object supervisingDepartment;
    public Object residingCountryCode;
    public List<Object> residingCountryCodeDescription;
    public Object residingCountryDescription;
    public Object profitCentre;
    public Object countryOfBirth;
    public Object wmsIndicator;
    public Object currentDesignation;
    public Object fxTierGroup;
    public Object faxIndemnity;
    public Object taxDeduction;
    public Object isSanctionChecked;
    public Object minorIndicatorFlag;
    public Object minorIndicator;
    public Object residentIndicatorFlag;
    public Object residentIndicator;
    public List<Object> relationshipDetails;
    public Object customerRelationshipStartDate;
    public Object primaryServiceCentre;
    public Object placeOfBirth;
}

public class EducationDetail{
    public Object qualification;
    public Object university;
}

public class EmploymentDetails{
    public Object employmentStatus;
    public Object nameOfEmployer;
    public Object jobTitleCode;
    public List<Object> jobTitleCodeDescription;
    public Object jobTitleDescription;
    public Object occupationCode;
    public List<Object> occupationCodeDescription;
    public Object occupationDescription;
    public Object periodOfEmployment;
    public Object employerIndustry;
    public Object employerLocation;
    public Object employeeId;
}

public class EmailInfo{
    public String email;
    public Object palm;
    public String emailTypeAndSuffix;
    public String type;
    public String typeSuffix;
    public Object endDate;
    public String preferenceFlag;
    public Object startDate;
    public String antiSpamIndicator;
    public long lastUpdatedDate;
}

public class PhoneInfo{
    public Object startDate;
    public Object endDate;
    public String phone;
    public Object cityCode;
    public String countryCode;
    public Object localCode;
    public String phoneTypeAndSuffix;
    public String type;
    public String typeSuffix;
    public String preferenceFlag;
    public Object workExtensionNumber;
    public Object lastUpdateDate;
}

public class MiscellaneousInfo{
    public Object fatcaInternalField;
    public Object dateOnForm;
    public Object fatcaDeleteIndicator;
    public Object fatcaStatus;
    public Object fatcaReviewStatusUpdatedDate;
    public Object withholdingCertType;
    public Object fatcaCountry;
    public Object fatcaReviewStatus;
    public Object type;
}

public class Root{
    public String globalCustomerId;
    public Object customerId;
    public String sourceCustomerId;
    public String customerSystemId;
    public BlacklistAndNegativelistDetails blacklistAndNegativelistDetails;
    public List<Address> addresses;
    public List<Object> documentInfo;
    public DemographicInfo demographicInfo;
    public List<Object> donotContactChannelDetails;
    public GeneralInfo generalInfo;
    public ExtendedGeneralInfo extendedGeneralInfo;
    public CorporateCustomerInfo corporateCustomerInfo;
    public RetailCustomerInfo retailCustomerInfo;
    public List<EducationDetail> educationDetails;
    public EmploymentDetails employmentDetails;
    public List<EmailInfo> emailInfo;
    public List<PhoneInfo> phoneInfo;
    public Object corporateIndicator;
    public Object preferredContactType;
    public Object preferredEmailType;
    public MiscellaneousInfo miscellaneousInfo;
    public Object preferredDocumentCode;
    public Object defaultAddressType;
    public Object preferredUniqueId;
}

