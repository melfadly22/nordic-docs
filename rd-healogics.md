# Registry Direct -> Healogics
  - [Submission Processing](#submission-processing)
  - [Data Validation](#data-validation)
    - [New Implementations](#new-implementations)
    - [Initial Patient Validation](#initial-patient-validation)
    - [Batch Patient Validation](#batch-patient-validation)

## Submission Processing

Lorem ipsum dolor sit amet. Est voluptatem natus a dolorem ratione nam iusto nobis. Sed labore quae et cupiditate dolores nam tempore autem et amet cupiditate.

Ad quam nihil et maiores optio et possimus consequatur et numquam beatae et perferendis alias. Ab facilis cumque qui sunt quos qui aspernatur quia.

?>Sit doloremque temporibus cum quibusdam accusamus ad nobis natus. Hic aliquam nulla qui voluptatem voluptatem a voluptatem totam ut natus recusandae qui porro aspernatur et perferendis eveniet rem dolorem iusto?

## Data Validation

### New Implementations

This section covers the steps and details that take place during the data validation process when implementing Registry Direct with a new healthcare organization before production go-live. The data validation process is typically scheduled once the first phase of the data mapping is completed.

?>There are two data validation processes: production submission data validation which happens periodically after going live with Registry Direct and pre-production data validation which is a one-time process that happens during a new implementation project. This section covers the latter.

The data validation process for new implementations will typically have two phases:

### Initial Patient Validation

During this process, one specific patient is chosen randomly and the only its data is submitted to be processed by Registry Direct with the feature to generate the validation file enabled. Once processed, Nordic engineers will review the data that resulted for the processed patient for any errors and will correct them as soon as possible.

In addition, Nordic will email the corresponding validation file to the health organization’s representative responsible with validating that the data was processed by Registry Direct as expected. Feedback will be provided at the data element level directly in the validation file using the corresponding columns.

Nordic’s development team will resolve all reported issues based on the feedback provided in the validation file and will prepare Registry Direct to resubmit the data for the same patient as soon as possible.

This process will repeat until there are no more issues with the initial patient chosen for the validation process.

?>This process can be extended to at least 10 patients where each patient is submitted and validated individually before moving on to the next patient.

### Batch Patient Validation

This can be considered as the second phase of the data validation process and during this phase, batch files, ideally with at least 30 patients should be submitted to Registry Direct for processing with the validation files generation feature enabled.

After each submission, the validation files will be emailed to the health organization’s representative that is responsible with validating that the data was processed by Registry Direct as expected. The representative will randomly choose 5 patients to review during this process and if there are any issues, report them directly in the validation files using the corresponding columns for providing feedback.

?>Each patient will generate one validation file so during each batch, five validation files should be reviewed and sent back to Nordic.

Nordic’s development team will resolve all reported issues based on the feedback provided in the validation files and will prepare Registry Direct to resubmit the data for the same patient as soon as possible.

This process should repeat for at least 8 days of data runs/submissions and ideally will be done with production like data.