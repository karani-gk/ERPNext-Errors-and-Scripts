<b>#ERRORS</b> <br/>

Frappe/ERPNext: erpnext TabError: inconsistent use of tabs and spaces in indentation

    Run the following pep8 command on the directory of the file producing the error:

    autopep8 -i my_file.py

<b>#SCRIPRS</b> <br/>

Frappe/ERPNext:  You need to add Barcode at the instance of creating a new record; Let's say for example, you want to add a barcode automatically when creating a patient.
First, create the Barcode field in the patient DocType. In this example, the field has a label 'Patient Barcode'

    Locate the file: erpnext/apps/erpnext/erpnext/healthcare/doctype/patient.py

    Add the below code to create the barcode:

    def before_insert(self):
        self.patient_barcode = self.first_name

Frappe/ERPNext: Get the details of the logged in user and store it in the added_by field

    self.added_by = frappe.session.user
    
    

Frappe/ERPNext: Filter items, return only the ones with a belong to a specific group

    frappe.ui.form.on('Vital Signs', {
        setup: function(frm) {
            frm.set_query("drug_allergy", function() {
                return  {
                    filters: {
                        item_group: 'Reusable'
                    }
                }
            });
        }
    });
    
    
Remove PoweredBy from footer
       /home/frappe/frappe-bench/apps/erpnext/erpnext/templates/includes/footer/footer_powered.html
