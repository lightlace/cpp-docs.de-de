---
title: MFC-Makros und globale Variablen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d26b374e233326ac5acc97486edc8d38e6bf5d81
ms.openlocfilehash: 75db28c7be1ab497ba9656136d22b114b488c4ae
ms.lasthandoff: 02/24/2017

---
# <a name="mfc-macros-and-globals"></a>MFC-Makros, globale Funktionen und globale Variablen
Die Microsoft Foundation Class-Bibliothek kann in zwei Hauptabschnitte unterteilt werden: (1) die MFC-Klassen und (2) Makros und Globals. Wenn eine Funktion oder eine Variable kein Member einer Klasse ist, ist es eine globale Funktion oder Variable.  
  
 Die MFC-Bibliothek und die ATL (Active Template Library) nutzen Makros für die Zeichenfolgenkonvertierung gemeinsam. Weitere Informationen finden Sie unter [Zeichenfolgenkonvertierungsmakros](../../atl/reference/string-conversion-macros.md) in der ATL-Dokumentation.  
  
 Die MFC-Makros und -Globals bieten Funktionen in den folgenden Kategorien.  
  
## <a name="general-mfc"></a>MFC allgemein  
  
-   [Datentypen](../../mfc/reference/data-types-mfc.md)  
  
-   [Typumwandlung von MFC-Klassenobjekten](../../mfc/reference/type-casting-of-mfc-class-objects.md)  
  
-   [Laufzeit-Dienste für laufzeitobjektmodelle](../../mfc/reference/run-time-object-model-services.md)  
  
-   [Diagnosedienste](../../mfc/reference/diagnostic-services.md)  
  
-   [Ausnahmeverarbeitung](../../mfc/reference/exception-processing.md)  
  
-   [CString-Formatierung und meldungsfeldanzeige](../../mfc/reference/cstring-formatting-and-message-box-display.md)  
  
-   [Meldungszuordnungen](../../mfc/reference/message-map-macros-mfc.md)  
  
-   [Anwendungsinformationen und Verwaltung](../../mfc/reference/application-information-and-management.md)  
  
-   [Standardbefehls- und Fenster-IDs](../../mfc/reference/standard-command-and-window-ids.md)  
  
-   [Die Auflistungsklasse](../../mfc/reference/collection-class-helpers.md)  
  
-   [Grau dargestellte und gerasterte bitmapfunktionen](../../mfc/reference/gray-and-dithered-bitmap-functions.md)  
  
-   [Standardroutinen Dialogdatenaustausch (DDX) für Dialogfelddaten](../../mfc/reference/standard-dialog-data-exchange-routines.md)  
  
-   [Standardroutinen Überprüfung (DDV) für Dialogfelddaten](../../mfc/reference/standard-dialog-data-validation-routines.md)  
  
-   [AFX-Meldungen](../../mfc/reference/afx-messages.md)  
  
-   [Steuerelementtypen für die Symbolleiste](../../mfc/reference/toolbar-control-styles.md)  
  
-   [CMFCImagePaintArea::IMAGE_EDIT_MODE-Enumeration](cmfcimagepaintarea-image-edit-mode-enumeration.md)  

  
## <a name="database"></a>Datenbank  
  
-   [Datensatzfeldaustausch (RFX) Funktionen](../../mfc/reference/record-field-exchange-functions.md) und [Massen-Datensatzfeldaustausch (Bulk-RFX) Funktionen](../../mfc/reference/record-field-exchange-functions.md) für die MFC-ODBC-Klassen  
  
-   [Datensatzfeldaustausch (DFX) Funktionen](../../mfc/reference/record-field-exchange-functions.md) für die MFC-DAO-Klassen  
  
-   [Funktionen für den Dialogdatenaustausch (DDX) für CRecordView und CDaoRecordView](../../mfc/reference/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (MFC-ODBC und DAO-Klassen)  
  
-   [Dialogdatenaustausch (DDX)-Funktionen für OLE-Steuerelemente](../../mfc/reference/dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [Makros und Globals, die das direkte Aufrufen von Open Database Connectivity (ODBC)-API-Funktionen unterstützen](../../mfc/reference/database-macros-and-globals.md)  
  
-   [DAO-Datenbank-Engine-Initialisierung und Beendigung](../../mfc/reference/dao-database-engine-initialization-and-termination.md)  
  
## <a name="internet"></a>Internet  
  
-   [Globals für das Analysieren von Internet-URL](../../mfc/reference/internet-url-parsing-globals.md)  
  
## <a name="dhtml--dhtml-event-maps"></a>DHTML-/DHTML-Ereigniszuordnungen  
  
-   [DHTML-Dialogdatenaustausch (DDX) Hilfsmakros](../../mfc/reference/ddx-dhtml-helper-macros.md)  
  
-   [DHTML-ereigniszuordnungen](../../mfc/reference/dhtml-event-maps.md)  
  
## <a name="ole"></a>OLE  
  
-   [OLE-Initialisierung](../../mfc/reference/ole-initialization.md)  
  
-   [Anwendungssteuerelement](../../mfc/reference/application-control.md)  
  
-   [Dispatchzuordnungen](../../mfc/reference/dispatch-maps.md)  
  
 Darüber hinaus bietet MFC eine Funktion namens [AfxEnableControlContainer](http://msdn.microsoft.com/library/7aa0b9d2-5329-4bc3-9d41-856e30fe2c2b) , ermöglicht, alle OLE-Container entwickelt, mit MFC 4.0 wurden mit vollständiger Unterstützung OLE-Steuerelemente eingebetteter.  
  
## <a name="ole-controls"></a>OLE-Steuerelemente  
  
-   [Variante parametertypkonstanten](../../mfc/reference/variant-parameter-type-constants.md)  
  
-   [Zugreifen auf die Typbibliothek](../../mfc/reference/type-library-access.md)  
  
-   [Eigenschaftenseiten](../../mfc/reference/property-pages-mfc.md)  
  
-   [Ereigniszuordnungen](../../mfc/reference/event-maps.md)  
  
-   [Ereignissenkenzuordnungen](../../mfc/reference/event-sink-maps.md)  
  
-   [Verbindungszuordnungen](../../mfc/reference/connection-maps.md)  
  
-   [Registrieren von OLE-Steuerelementen](../../mfc/reference/registering-ole-controls.md)  
  
-   [Klassenfactorys und Lizenzierung](../../mfc/reference/class-factories-and-licensing.md)  
  
-   [Persistenz der OLE-Steuerelemente](../../mfc/reference/persistence-of-ole-controls.md)  
  
 Im ersten Teil dieses Abschnitts wird kurz auf die einzelnen der oben genannten Kategorien eingegangen. Darüber hinaus werden die Globals und Makros in der Kategorie zusammen mit einer kurzen Beschreibung der Funktionen aufgeführt. Anschließend folgt eine Beschreibung der globalen Funktionen, der globalen Variablen und der Makros in der MFC-Bibliothek.  
  
> [!NOTE]
>  Viele globale Funktionen beginnen mit dem Präfix "Afx". Einige Funktionen, beispielsweise die Funktionen für den Dialogdatenaustausch (DDX) sowie viele Datenbankfunktionen, entsprechen dieser Konvention jedoch nicht. Alle globalen Variablen beginnen mit "afx" als Präfix. Makros beginnen nicht mit einem bestimmten Präfix, werden aber in Großbuchstaben geschrieben.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../mfc/class-library-overview.md)




