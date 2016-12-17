---
title: "MFC-Makros, globale Funktionen und globale Variablen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Afx-Namenskonvention"
  - "Globale Funktionen"
  - "Globale Funktionen, MFC"
  - "Globale Variablen, MFC"
  - "Makros"
  - "Makros, MFC"
  - "MFC, Globale Funktionen und Variablen"
  - "MFC, Makros"
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
caps.latest.revision: 18
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-Makros, globale Funktionen und globale Variablen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Microsoft Foundation Class\-Bibliothek kann in zwei Hauptabschnitte unterteilt werden: \(1\) die MFC\-Klassen und \(2\) Makros und Globals.  Wenn eine Funktion oder eine Variable kein Member einer Klasse ist, ist es eine globale Funktion oder Variable.  
  
 Die MFC\-Bibliothek und die ATL \(Active Template Library\) nutzen Makros für die Zeichenfolgenkonvertierung gemeinsam.  Weitere Informationen finden Sie in der ATL\-Dokumentation unter [String Conversion Macros](../../atl/reference/string-conversion-macros.md).  
  
 Die MFC\-Makros und \-Globals bieten Funktionen in den folgenden Kategorien.  
  
## MFC allgemein  
  
-   [Datentypen](../../mfc/reference/data-types-mfc.md)  
  
-   [Typumwandlung von MFC\-Klassenobjekten](../../mfc/reference/type-casting-of-mfc-class-objects.md)  
  
-   [Dienste für Laufzeitobjektmodelle](../../mfc/reference/run-time-object-model-services.md)  
  
-   [Diagnosedienste](../../mfc/reference/diagnostic-services.md)  
  
-   [Ausnahmeverarbeitung](../../mfc/reference/exception-processing.md)  
  
-   [CString\-Formatierung und Meldungsfeldanzeige](../../mfc/reference/cstring-formatting-and-message-box-display.md)  
  
-   [Meldungszuordnungen](../../mfc/reference/message-map-macros-mfc.md)  
  
-   [Anwendungsinformationen und Verwaltung](../../mfc/reference/application-information-and-management.md)  
  
-   [Standardbefehls\- und Fenster\-IDs](../../mfc/reference/standard-command-and-window-ids.md)  
  
-   [Auflistungsklassenhilfen](../../mfc/reference/collection-class-helpers.md)  
  
-   [Grau dargestellte und gerasterte Bitmapfunktionen](../../mfc/reference/gray-and-dithered-bitmap-functions.md)  
  
-   [Standardroutinen für den Dialogdatenaustausch \(Dialog Data Exchange, DDX\)](../../mfc/reference/standard-dialog-data-exchange-routines.md)  
  
-   [Standardroutinen für die Dialogfelddatenvalidierung \(Dialog Data Validation, DDV\)](../../mfc/reference/standard-dialog-data-validation-routines.md)  
  
-   [AFX\-Meldungen](../../mfc/reference/afx-messages.md)  
  
-   [Steuerelementtypen für die Symbolleiste](../../mfc/reference/toolbar-control-styles.md)  
  
-   [CMFCImagePaintArea::IMAGE\_EDIT\_MODE Enumeration](../../mfc/reference/cmfcimagepaintarea-image-edit-mode-enumeration.md)  
  
## Datenbank  
  
-   [Funktionen für den Datensatzfeldaustausch \(Record Field Exchange, RFX\)](../../mfc/reference/record-field-exchange-functions.md) und [Funktionen für den Sammel\-Datensatzfeldaustausch \(Bulk Record Field Exchange, Bulk\-RFX\)](../../mfc/reference/record-field-exchange-functions.md) für die MFC\-ODBC\-Klassen  
  
-   [Funktionen für den Datensatzfeldaustausch \(DFX\)](../../mfc/reference/record-field-exchange-functions.md) für die MFC\-DAO\-Klassen  
  
-   [Funktionen für den Dialogdatenaustausch \(Dialog Data Exchange, DDX\) für CRecordView und CDaoRecordView](../../mfc/reference/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) \(MFC\-ODBC\- und \-DAO\-Klassen\)  
  
-   [Funktionen für den Dialogdatenaustausch \(DDX\) für OLE\-Steuerelemente](../../mfc/reference/dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [Makros und Globals, die das direkte Aufrufen von Open Database Connectivity\(ODBC\)\-API\-Funktionen unterstützen](../../mfc/reference/database-macros-and-globals.md)  
  
-   [Initialisierung und Terminierung des DAO\-Datenbankmoduls](../../mfc/reference/dao-database-engine-initialization-and-termination.md)  
  
## Internet  
  
-   [Globals für das Analysieren von Internet\-URLs](../../mfc/reference/internet-url-parsing-globals.md)  
  
## DHTML\-\/DHTML\-Ereigniszuordnungen  
  
-   [Hilfsmakros für den DHTML\-Dialogdatenaustausch \(DDX\)](../../mfc/reference/ddx-dhtml-helper-macros.md)  
  
-   [DHTML\-Ereigniszuordnungen](../../mfc/reference/dhtml-event-maps.md)  
  
## OLE  
  
-   [OLE\-Initialisierung](../../mfc/reference/ole-initialization.md)  
  
-   [Anwendungssteuerung](../../mfc/reference/application-control.md)  
  
-   [Dispatchzuordnungen](../../mfc/reference/dispatch-maps.md)  
  
 Darüber hinaus bietet MFC eine Funktion mit dem Namen [AfxEnableControlContainer](../Topic/AfxEnableControlContainer.md), die die vollständige Unterstützung eingebetteter OLE\-Steuerelemente durch alle OLE\-Container ermöglicht, die mit MFC 4.0 entwickelt wurden.  
  
## OLE\-Steuerelemente  
  
-   [Variante Parametertypkonstanten](../../mfc/reference/variant-parameter-type-constants.md)  
  
-   [Typbibliothekszugriff](../../mfc/reference/type-library-access.md)  
  
-   [Eigenschaftenseiten](../../mfc/reference/property-pages-mfc.md)  
  
-   [Ereigniszuordnungen](../../mfc/reference/event-maps.md)  
  
-   [Ereignissenkenzuordnungen](../../mfc/reference/event-sink-maps.md)  
  
-   [Verbindungszuordnungen](../../mfc/reference/connection-maps.md)  
  
-   [Registrieren von OLE\-Steuerelementen](../../mfc/reference/registering-ole-controls.md)  
  
-   [Klassenfactorys und Lizenzierung](../../mfc/reference/class-factories-and-licensing.md)  
  
-   [Dauerhaftigkeit von OLE\-Steuerelementen](../../mfc/reference/persistence-of-ole-controls.md)  
  
 Im ersten Teil dieses Abschnitts wird kurz auf die einzelnen der oben genannten Kategorien eingegangen. Darüber hinaus werden die Globals und Makros in der Kategorie zusammen mit einer kurzen Beschreibung der Funktionen aufgeführt.  Anschließend folgt eine Beschreibung der globalen Funktionen, der globalen Variablen und der Makros in der MFC\-Bibliothek.  
  
> [!NOTE]
>  Viele globale Funktionen beginnen mit dem Präfix "Afx". Einige Funktionen, beispielsweise die Funktionen für den Dialogdatenaustausch \(DDX\) sowie viele Datenbankfunktionen, entsprechen dieser Konvention jedoch nicht.  Alle globalen Variablen beginnen mit "afx" als Präfix.  Makros beginnen nicht mit einem bestimmten Präfix, werden aber in Großbuchstaben geschrieben.  
  
## Siehe auch  
 [Klassenübersicht](../../mfc/class-library-overview.md)