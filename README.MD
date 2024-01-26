THIS CODE IS FOR PRICING RULES TO WORK WITH PAYMENT TERMS IN ERPNEXT

ADDED CODE IN 

frappe-bench/apps/erpnext/erpnext/selling/sales_common.js

campaign: function() {
		this.apply_pricing_rule();
},

/* ADDED THIS LINE TO ADD PRICING RULE BASE ON PAYMENT TERMS CONDITION */
payment_terms_template: function() {
		this.apply_pricing_rule();
},
/********************************************************************/


frappe-bench/apps/erpnext/erpnext/
