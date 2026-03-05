## Procurement, Inbound & Global Trade Management Module

# 1. Module Overview

The Procurement, Inbound & Global Trade Management Module enables organizations to manage vendor procurement, purchase orders, inbound logistics, and international trade operations within a unified platform.

The system ensures procurement decisions align with:

merchandising plans

financial budgets (OTB)

vendor contracts

tax regulations

international trade compliance

It also provides real-time visibility into inbound shipments and imported inventory while supporting export operations for global distribution.

The module integrates closely with:

Retail Planning Platform

Inventory Decision Engine

Warehouse Management System

Finance and ERP systems

# 2. Key Objectives

The module aims to:

• streamline vendor procurement workflows
• enforce financial discipline through OTB governance
• automate tax and landed cost calculations
• provide real-time inbound shipment visibility
• enable vendor collaboration through digital portals
• manage import compliance and logistics documentation
• support export planning for international distribution

# 3. User Personas
Category Managers

Raise purchase orders and manage buying decisions.

Procurement Teams

Manage vendor relationships and procurement budgets.

Finance Teams

Ensure procurement aligns with financial planning and tax compliance.

Supply Chain Teams

Track inbound shipments and warehouse readiness.

Vendors / Manufacturers

Confirm purchase orders and dispatch shipments.

Global Trade / Logistics Teams

Manage import and export documentation and compliance.

# 4. Module Architecture

The system consists of three major functional components.

Vendor & Procurement Management
Inbound Supply Visibility
Global Trade Management (Import & Export)

# 5. Vendor & Procurement Management
Vendor Master Management

The Vendor Master maintains all vendor information required for procurement operations.

Key Vendor Attributes

Vendor Legal Name
GSTIN
PAN
Payment Terms (Net 30 / Net 60)
Lead Time
Vendor Margin %

Validation Rules

• GSTIN must follow a 15-character format
• Duplicate vendors blocked based on PAN or mobile number

Business Impact

Centralized vendor information ensures procurement accuracy and prevents duplicate vendor records.

# Open-To-Buy (OTB) Budget Control

Before raising a purchase order, the system checks the available Open-To-Buy (OTB) budget.

OTB budgets are defined by:

category

season

financial plan

# Logic

If the purchase order value exceeds the available OTB budget, submission is blocked.

Override is allowed only for authorized roles.

Example:

If PO Value > Available OTB
→ Block submission
→ Allow override only for Director role
Business Impact

Ensures procurement aligns with financial planning and inventory investment limits.

# Purchase Order Creation & Versioning

The system enables structured purchase order management.

Capabilities

• create purchase orders linked to vendors and warehouses
• maintain version history for edits (V1, V2, V3)
• allow revision tracking and audit trails

Rule

Purchase orders cannot be edited once inbound processing begins.

Example:

If GRN Started = TRUE
→ PO becomes locked
Business Impact

Ensures procurement transparency and prevents operational inconsistencies.

# Automated Tax Calculation

The system automatically calculates applicable taxes based on vendor location.

Tax Logic
Vendor State = Warehouse State
→ CGST + SGST

Vendor State ≠ Warehouse State
→ IGST
Business Impact

Ensures GST compliance and eliminates manual tax calculation errors.

# Landed Cost Calculation

The system calculates true landed cost per unit by incorporating logistics and duty costs.

Cost Components

Purchase Cost
Freight
Custom Duty
Handling Charges
Insurance

Formula
Landed Cost per Unit =
(Purchase Cost + Freight + Duty + Insurance) / Quantity
Business Impact

Provides accurate cost basis for pricing and margin analysis.

# Approval Workflow

Purchase orders must follow a structured approval hierarchy.

Approval Logic
PO Value	Approval Required
< ₹1L	Auto Approved
₹1L – ₹5L	Manager Approval
> ₹5L	CXO Approval

Notifications are sent through email and application alerts.

Business Impact

Ensures procurement governance and prevents unauthorized spending.

# 6. Inbound Supply Management

After purchase orders are issued, the system manages inbound shipments through ASN and shipment tracking.

# Vendor Portal

Vendors access a portal to manage order fulfillment.

Capabilities include:

• view purchase orders
• download packing instructions
• confirm shipment quantities

Vendor confirmation is mandatory before dispatch.

# Box Scanning

Before shipment leaves the vendor facility, cartons must be scanned.

Logic
ASN creation blocked if cartons not scanned
Business Impact

Ensures shipment accuracy and improves warehouse preparation.

# Advance Shipment Notice (ASN)

ASN provides advance visibility of incoming inventory.

ASN Data Includes

SKU
Quantity
Shipment Date
Expected Arrival Date

Business Impact

Enables warehouse teams to prepare for inbound processing.

# Inbound Visibility Dashboard

The system provides a dashboard showing upcoming shipments.

Example:

500 Red Shirts arriving Tuesday

Capabilities include:

• tracking shipment status
• monitoring expected vs actual quantities
• identifying delays

# ASN to GRN Matching

During goods receipt, ASN data is matched with warehouse receipts.

Validation Logic

If variance between ASN and received quantity exceeds tolerance:

Block GRN processing
Business Impact

Improves inventory accuracy and prevents receiving discrepancies.

# 7. Import Management

For global sourcing, the system must support import logistics and compliance.

# Import Documentation Management

The system stores key import documents.

Examples include:

Commercial Invoice
Packing List
Bill of Lading
Certificate of Origin
Import Licenses

These documents are linked to purchase orders.

Import Shipment Tracking

Track international shipments across logistics stages.

Stages include:

Factory Dispatch
↓
Port of Origin
↓
Ocean / Air Transit
↓
Destination Port
↓
Customs Clearance
↓
Warehouse Delivery

Business Impact

Provides visibility into international supply chain operations.

# Customs Duty & Import Costing

Import duties and additional charges must be included in landed cost calculations.

Cost components include:

Customs Duty
Import GST
Port Handling Charges
Freight
Insurance

These costs feed into the landed cost calculation engine.

# 8. Export Management

For D2C brands exporting to distributors or international marketplaces.

Export Order Management

Export orders are created for international customers or distributors.

Capabilities include:

• export-specific pricing
• international shipping instructions
• export invoice generation

Export Compliance

The system must manage export documentation.

Examples include:

Commercial Invoice
Packing List
Shipping Bill
Export Declaration

Export Logistics Tracking

Track export shipments from warehouse to destination.

Stages include:

Warehouse Dispatch
↓
Port Shipment
↓
International Transit
↓
Destination Delivery

# 9. Success Metrics

The effectiveness of the module will be measured through:

Procurement Efficiency
• purchase order cycle time

Budget Compliance
• percentage of procurement within OTB limits

Inbound Accuracy
• ASN vs GRN variance rate

Vendor Performance
• on-time dispatch rate

Import Efficiency
• customs clearance time

Export Efficiency
• export order fulfillment time

# 10. Integration with Commerce Systems

The module integrates with:

Retail Planning Platform
Inventory Decision Engine
Warehouse Management System
Finance / ERP Systems
Vendor Portals
Logistics Platforms

This ensures procurement decisions align with merchandising strategy and operational execution.
