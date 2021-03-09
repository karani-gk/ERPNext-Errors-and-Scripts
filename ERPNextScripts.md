#ERRORS
erpnext TabError: inconsistent use of tabs and spaces in indentation

    Run the following pep8 command on the directory of the file producing the error:

    autopep8 -i my_file.py

#SCRIPRS
You need to add Barcode at the instance of creating a new record; Lets say for example, you want to add a barcode automatically when creating a patient
First, create the Barcode field in the patient DocType. In this example, the field has a label 'Patient Barcode'

    Locate the file: erpnext/apps/erpnext/erpnext/healthcare/doctype/patient.py

    Add the below code to create the barcode:

    def before_insert(self):
        self.patient_barcode = self.first_name
