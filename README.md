Pharmacy Stock Requisition Tool

🔹 Purpose

This workbook helps to manage stock requisition by calculating shortages and reorder quantities while respecting each item’s Minimum Order Quantity (MOQ).

🔹 How It Works

Available → Current stock balance.

Target → Desired stock level (e.g., two weeks supply).

MOQ → Minimum order quantity, based on pack size (14, 28, 60, etc.).

Reorder → Formula that decides how much to order:

If stock < target → order shortage or MOQ (whichever is greater).

If stock ≥ target → reorder = 0.

Orders are rounded to nearest MOQ pack size.

🔹 Formulas Used

MOQ
=IF([@[AVAILABLE STOCK]]=0,1,IFERROR(XLOOKUP(TRUE, MOD([@[AVAILABLE STOCK]],$L$2:$L$4)=0,$K$2:$K$4),1))

Reorder

=IF([@[TARGET STOCK]]-[@[AVAILABLE STOCK]]>0,MAX([@[TARGET STOCK]]-[@[AVAILABLE STOCK]],[@MOQ]),0)

🔹 How to Update

To add a new product, enter its Available and Target.

To add a new MOQ pack size, update the MOQ lookup list (columns H & I).

The formulas will automatically recalculate.

🔹 Notes

If #N/A appears → means the item’s pack size is not in the MOQ lookup list.

Always verify MOQ values before placing final orders.

🔹 Author

Created by: [Adjoa oforiwaa Thompson]
Date: [02/08/2025]

# pharmacy-stock-requisition-tool
