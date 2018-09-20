---
title: MFC-Makros und Globals | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions [MFC]
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d5e735a78f35ac799678b077b7933c6134d568e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386185"
---
# <a name="mfc-macros-and-globals"></a>MFC-Makros, globale Funktionen und globale Variablen

Die Microsoft Foundation Class-Bibliothek kann in zwei Hauptabschnitte unterteilt werden: (1) die MFC-Klassen und (2) Makros und Globals. Wenn eine Funktion oder eine Variable kein Member einer Klasse ist, ist es eine globale Funktion oder Variable.

Die MFC-Bibliothek und die ATL (Active Template Library) nutzen Makros für die Zeichenfolgenkonvertierung gemeinsam. Weitere Informationen finden Sie unter [Zeichenfolgen-Konvertierungsmakros](../../atl/reference/string-conversion-macros.md) in der ATL-Dokumentation.

Die MFC-Makros und -Globals bieten Funktionen in den folgenden Kategorien.

## <a name="general-mfc"></a>MFC allgemein

- [Datentypen](data-types-mfc.md)

- [Typumwandlung von MFC-Klassenobjekten](type-casting-of-mfc-class-objects.md)

- [Laufzeit-Dienste für laufzeitobjektmodelle](run-time-object-model-services.md)

- [Diagnosedienste](diagnostic-services.md)

- [Ausnahmeverarbeitung](exception-processing.md)

- [CString-Formatierung und meldungsfeldanzeige](cstring-formatting-and-message-box-display.md)

- [Meldungszuordnungen](message-map-macros-mfc.md)

- [Delegaten und Schnittstellenzuordnungen](delegate-and-interface-maps.md)

- [Module und DLLs](extension-dll-macros.md)

- [Anwendungsinformationen und anwendungsverwaltung](application-information-and-management.md)

- [Standard Standardbefehls- und Fenster-IDs](standard-command-and-window-ids.md)

- [Die Auflistungsklasse](collection-class-helpers.md)

- [Zu ausgrauen und Dithering Bitmap-Funktionen](gray-and-dithered-bitmap-functions.md)

- [Standard Dialogdatenaustausch (DDX)-Routinen](standard-dialog-data-exchange-routines.md)

- [Standard (DDV)-Validierung der Dialogfelddaten](standard-dialog-data-validation-routines.md)

- [AFX-Meldungen](afx-messages.md)

- [Steuerelementstile für die Symbolleiste](toolbar-control-styles.md)

- [CMFCImagePaintArea::IMAGE_EDIT_MODE-Enumeration](cmfcimagepaintarea-image-edit-mode-enumeration.md)


## <a name="database"></a>Datenbank

- [Datensatzfeldaustausch (RFX) Datensatzfunktionen](record-field-exchange-functions.md) und [Massen-Datensatzfeldaustausch (Bulk-RFX) Funktionen](record-field-exchange-functions.md) für die MFC-ODBC-Klassen

- [Notieren Sie die Datensatzfeldaustausch (DFX)-Funktionen](record-field-exchange-functions.md) für die MFC-DAO-Klassen

- [Dialogdatenaustausch (DDX)-Funktionen für CRecordView und CDaoRecordView](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (MFC-ODBC und DAO-Klassen)

- [Dialogdatenaustausch (DDX)-Funktionen für OLE-Steuerelemente](dialog-data-exchange-functions-for-ole-controls.md)

- [Makros und Globals, bei der direktes Aufrufen von Open Database Connectivity (ODBC)-API-Funktionen](database-macros-and-globals.md)

- [DAO-Datenbank-Engine-Initialisierung und Beendigung](dao-database-engine-initialization-and-termination.md)

## <a name="internet"></a>Internet

- [Globals für das Analysieren der Internet-URL](internet-url-parsing-globals.md)

## <a name="dhtml--dhtml-event-maps"></a>DHTML-/DHTML-Ereigniszuordnungen

- [DHTML-Dialogdatenaustausch (DDX)-Hilfsmakros](ddx-dhtml-helper-macros.md)

- [DHTML-ereigniszuordnungen](dhtml-event-maps.md)

## <a name="ole"></a>OLE

- [OLE-Initialisierung](ole-initialization.md)

- [Die anwendungssteuerung](application-control.md)

- [Dispatchzuordnungen](dispatch-maps.md)

Darüber hinaus bietet MFC eine Funktion namens [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) , ermöglicht, die alle OLE-Container mit MFC 4.0 entwickelt für die vollständige Unterstützung OLE-Steuerelemente eingebetteter.

## <a name="ole-controls"></a>OLE-Steuerelemente

- [Variant-parametertypkonstanten](variant-parameter-type-constants.md)

- [Zugreifen auf die Typbibliothek](type-library-access.md)

- [Eigenschaftenseiten](property-pages-mfc.md)

- [Ereigniszuordnungen](event-maps.md)

- [Ereignissenkenzuordnungen](event-sink-maps.md)

- [Verbindungszuordnungen](connection-maps.md)

- [Registrieren von OLE-Steuerelementen](registering-ole-controls.md)

- [Klassenfabriken und Lizenzierung](class-factories-and-licensing.md)

- [Persistenz der OLE-Steuerelemente](persistence-of-ole-controls.md)

Im ersten Teil dieses Abschnitts wird kurz auf die einzelnen der oben genannten Kategorien eingegangen. Darüber hinaus werden die Globals und Makros in der Kategorie zusammen mit einer kurzen Beschreibung der Funktionen aufgeführt. Anschließend folgt eine Beschreibung der globalen Funktionen, der globalen Variablen und der Makros in der MFC-Bibliothek.

> [!NOTE]
>  Viele globale Funktionen beginnen mit dem Präfix "Afx". Einige Funktionen, beispielsweise die Funktionen für den Dialogdatenaustausch (DDX) sowie viele Datenbankfunktionen, entsprechen dieser Konvention jedoch nicht. Alle globalen Variablen beginnen mit "afx" als Präfix. Makros beginnen nicht mit einem bestimmten Präfix, werden aber in Großbuchstaben geschrieben.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../mfc/class-library-overview.md)



