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


frappe-bench/apps/erpnext/erpnext/accounts/doctype/pricing_rule/pricing_rule.js

set_options_for_applicable_for: function(frm) {
	var options = [""];
	var applicable_for = frm.doc.applicable_for;
	/* ADDED PAYMENT TERMS TEMPLATE IN OPTION TO BE WORK WITH PAYMENT TERMS */
	if(frm.doc.selling) {
		options = $.merge(options, ["Customer", "Customer Group", "Territory", "Sales Partner", "Campaign", "Payment Terms Template"]);
	}
	if(frm.doc.buying) {
		$.merge(options, ["Supplier", "Supplier Group"]);
	}

	set_field_options("applicable_for", options.join("\n"));

	if(!in_list(options, applicable_for)) applicable_for = null;
	frm.set_value("applicable_for", applicable_for);
}

EDIT DOCTYPE IN ERPNEXT

