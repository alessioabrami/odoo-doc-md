# Hardware — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../employees.html "Dipendenti") |
  * [precedente](kiosks.html "Kiosks") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Presenze](../attendances.html) »
  * Hardware



# Hardware¶

Employees who are **not** database users, and therefore, do **not** have access to the _Attendances_ app, must sign in and out of work using a kiosk. The following are the physical requirements for setting up a kiosk.

## Kiosk devices¶

A kiosk is a self-service station, where employees can [check in and out of work](kiosks.html#attendances-kiosk-mode-entry) with either a badge or an RFID key fob. Typically, these devices are dedicated as kiosks only, but any device with an internet browser is able to be set up as a kiosk.

A kiosk is used by navigating to the webpage specified in the [configuration](kiosks.html#attendances-kiosk-settings) section of the _Attendances_ app.

Kiosks are set up using one of the following types of devices:

  * Laptop or Desktop computer

  * Tablet

  * Mobile phone (Android or iOS)




Suggerimento

Touchscreens are easy to use, and tablets and mobile phones take up less space. That’s why most consider using a smaller device with a touchscreen as a kiosk.

It is recommended to place kiosks on a secure stand, or mount them securely on a wall.

## Riconoscimenti¶

Badges are a way for employees to quickly sign in and out from a kiosk, as badges are scanned by the kiosk’s camera to quickly identify the employee.

To generate a badge, first navigate to the Employees app. Next, click on the desired employee card to open the employee’s form, then click the HR Settings tab.

Under the ATTENDANCE/POINT OF SALE/MANUFACTURING section, there is a Badge ID field. If this field is blank, click Generate at the end of the Badge ID line, and the field is automatically populated with a new badge ID number. Then, click Print Badge at the end of the badge ID number to create a PDF file of the badge.

If a badge ID number is already present on the employee form, there is no Generate button, only a Print Badge button.

The employee’s badge contains the employee’s photo, name, job position, company logo, and a barcode that can be scanned at a kiosk to check in and out.

Badges can be printed for employees using any thermal or inkjet printer.

Nota

Badges are **not** required, as employees can manually identify themselves on the kiosk.

### Lettori di codici a barre.¶

When using badges to check in and out, the barcode **must** be scanned to identify the employee. This can be done with the kiosk’s camera, if one is available on the device.

If a camera is **not** available on the kiosk device, an external barcode scanner must be used to scan badges.

Kiosks work with most USB barcode scanners. Bluetooth barcode scanners are also supported for devices without USB ports, or if a wireless connection is desired.

Follow the manufacturer’s instructions on the barcode scanner to properly connect the barcode scanner to the kiosk device.

Suggerimento

If the barcode scanner is connected directly to a computer, it [must be configured](../../inventory_and_mrp/barcode/setup/hardware.html) to use the computer’s keyboard layout.

Nota

An IoT box is **not** required to use a barcode scanner.

## RFID key fob readers¶

Instead of using a badge, employees can scan a personal RFID key fob with an RFID reader to check in and out of work.

It is **required** to purchase _both_ RFID key fobs and an RFID reader to use this method to check in and out. Follow the manufacturer’s directions to install the RFID reader, and set up the RFID key fob.

Suggerimento

A recommended RFID reader is the [Neuftech USB RFID Reader](https://neuftech.net/Neuftech-USB-RFID-Reader-ID-Kartenlesegerät-Kartenleser-Kontaktlos-Card-Reader-für-EM4100).

Nota

An IoT box is **not** required to use RFID key fobs.

[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/applications/hr/attendances/hardware.rst)

### Navigazione

  * [indice](../../../genindex.html "Indice generale")
  * [moduli](../../../py-modindex.html "Indice del modulo Python") |
  * [successivo](../employees.html "Dipendenti") |
  * [precedente](kiosks.html "Kiosks") |
  * [Odoo 17.0 documentazione](../../../index-2.html) »
  * [Documentazione Utente](../../../applications.html) »
  * [Human resources](../../hr.html) »
  * [Presenze](../attendances.html) »
  * Hardware


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration
  *[OCR]: optical character recognition
  *[AI]: Artificial Intelligence
  *[IAP]: In-App Purchase
  *[RTL]: right-to-left
  *[RST]: reStructuredText
  *[GUI]: graphical user interface
  *[TOC]: Table Of Contents
  *[SEO]: Search Engine Optimization
  *[EDI]: electronic data interchange
  *[SDD]: SEPA Direct Debit
  *[PLE]: Programa de Libros Electrónico
  *[BoM]: Bill of Materials
  *[MO]: Manufacturing Order
  *[MPS]: Master Production Schedules
  *[OEE]: overall equipment effectiveness
  *[RFQ]: Request for Quotation
  *[RfQ]: Request for Quotation
  *[RfQs]: Requests for Quotation
  *[IU]: Interfaccia Utente
  *[UoM]: Unit of Measure
  *[PoS]: Point of Sale
  *[FBM]: Fulfilled By Merchant
  *[FBA]: Fulfilled by Amazon
  *[API]: application programming interfaces
  *[IVA]: imposta sul valore aggiunto
  *[MRR]: Monthly Recurring Revenue
  *[ARR]: Annual Recurring Revenue
  *[USB]: Universal Serial Bus
  *[IoT]: Internet of Things
  *[OS]: Operating System
  *[SO]: sales order
  *[MRP]: Material Requirement Planning
  *[DNS]: Domain Name System
  *[SMTP]: Simple Mail Transfer Protocol
  *[SSL]: Secure Sockets Layer
  *[TLS]: Transport Layer Security
  *[SPF]: Sender Policy Framework
  *[DKIM]: DomainKeys Identified Mail
  *[DMARC]: Domain-based Message Authentication, Reporting, & Conformance
  *[CNAME]: nome canonico
  *[Cc]: Copia carbone
  *[LAN]: Local Area Network
  *[SSH]: secure shell protocol
  *[HTTPS]: Hypertext Transfer Protocol Secure
  *[UUID]: Universal Unique Identifier
  *[POS]: Punto vendita
  *[URL]: Uniform Resource Locator
  *[2FA]: two-factor authentication
  *[QR]: Quick Response
  *[LDAP]: Lightweight Directory Access Protocol
  *[KPI]: Indicatori di Prestazione Chiave
  *[ICP]: Indicatori Chiave di Prestazione
  *[CV]: curriculum vitae
  *[IAP’s]: in-app purchases
  *[DMFA]: De Multifunctionele Aangifte
  *[VIN]: Vehicle Identification Number
  *[MSRP]: Manufacturer's Suggested Retail Price