# Apperta Clinical Modelling Community - 5 Nation CDR project
Ian McNicoll <ian@inidus.com>
v1.0.0, 12-Nov-2017

Documentation published at https://clinicalmodelsuk.github.io/5NCDR/

## Aims of the 5N-CDR project

Within the UK and Irish ehealth communities there is considerable interest in establishing a set of 'common, standard' openEHR templates,
 based as far as possible on published international content towards these goals

- to record key clinical data as part of an EHR or PHR in a consistent fashion, either for longitudinal or episodic use
- to act as the source of data for [INTEROpen Care-Connect HL7 FHIR API](https://nhsconnect.github.io/CareConnectAPI/index.html) alignment, in the first instance `read` and `search` operations.
- maximise appropriate use of terminologies such as SNOMED CT, dm+d and LOINC, inline with national directives and market uptake.
- to include sufficient IHE-XDS bindings, particularly using the NHS SNOMED-CT Care Correspondence subset as the basis for XDS `type` metadata values,
  possibly to be exposed via a FHIR `DocumentReference` resource.


### Candidate openEHR templates::

- [IDCR - Adverse Reaction List.v1](http://ckm.apperta.org/ckm/#showTemplate_1051.57.71) -  `Adverse reaction list`
- `Problem list`
- `Immunisation list`
- `Medication statement`
- `Vital signs encounter`
- `Metabolic summary`

NOTE: The candidate templates are deliberately 'opinionated' and will not be suitable for all use-cases.

### Registering for Apperta CKM template reviews

To register for template reviews, please [sign up here.](http://ckm.apperta.org/ckm/#signUp_1051.61.18_3b7a82f9dafec941f229965394a0d590)

### High-level FHIR requirements

1. I want to access data held in an openEHR CDR as Allergies, Medications, Problems or Immunisations and expose that data via an HL7 FHIR facade, to be compliant with the UK Care-Connect STU3 profiles.

2. The `read`, `search` and `conformance` operations of the following Care-Connect STU3 Profiles should be supported.

WARNING: The links below refer to the FHIR STU2 profiles - formal STU3 documentation is in preparation.

- [AllergyIntolerance](https://nhsconnect.github.io/CareConnectAPI/api_clinical_allergyintolerance.html)
- [Condition](https://nhsconnect.github.io/CareConnectAPI/api_clinical_condition.html)
- [Immunization](https://nhsconnect.github.io/CareConnectAPI/api_medication_immunization.html)
- [MedicationStatement](https://nhsconnect.github.io/CareConnectAPI/api_medication_medicationstatement.html)

The `Vital signs encounter` and `Metabolic summary` templates have less of a clear relationship to a single Care-Connect Profile
 but will largely involve retrieving bundles of Observation resources.

 - [Observation](https://nhsconnect.github.io/CareConnectAPI/api_diagnostics_observation.html)

### STU3 profiles
[Github of Care-Connect STU3 profiles](https://github.com/nhsconnect/CareConnect-profiles/tree/feature/stu3)

3. All `mandatory` and `required` HL7 FHIR Care-connect data structure elements must be retrieved.
Guidance will be given for each template / profile as to which optional elements should be supported.

4. The handling of negated and missing data e.g. 'No known allergies or adverse reactions' is still being discussed by Care-Connect community. Advice will be given on mappings in due course.

## Detailed openEHR-FHIR mapping guidance (TBD)

- [AllergyIntolerance](https://github.com/inidus/open_ehr-fhir_care_connect/blob/master/docs/openEHR%20AdverseReactionRisk%20to%20FHIR%20allergyIntolerance%20STU3%20mappings.adoc)
- [Condition]
- [Immunization]
- [MedicationStatement]
