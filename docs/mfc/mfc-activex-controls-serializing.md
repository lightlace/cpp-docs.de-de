---
title: 'MFC-ActiveX-Steuerelemente: Serialisierung | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- _wVerMinor
- DoPropExchange
- _wVerMajor
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], version support
- wVerMinor global constant [MFC]
- GetVersion method [MFC]
- ExchangeVersion method [MFC]
- MFC ActiveX controls [MFC], serializing
- DoPropExchange method [MFC]
- versioning ActiveX controls
- wVerMajor global constant
ms.assetid: 9d57c290-dd8c-4853-b552-6f17f15ebedd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74d62411747dbe920b772b66d11cd1e2a789c5db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353497"
---
# <a name="mfc-activex-controls-serializing"></a>MFC-ActiveX-Steuerelemente: Serialisierung
In diesem Artikel wird erläutert, wie ein ActiveX-Steuerelement serialisiert wird. Serialisierung ist der Prozess der lesen oder Schreiben auf einem permanenten Speichermedium, z. B. eine Datenträgerdatei. Die Microsoft Foundation Class (MFC)-Bibliothek bietet integrierte Unterstützung für die Serialisierung in Klasse `CObject`. `COleControl` erweitert diese Unterstützung für ActiveX-Steuerelemente durch die Verwendung einer Eigenschaft Austauschmechanismus.  
  
 Serialisierung für ActiveX-Steuerelementen wird durch Überschreiben implementiert [COleControl:: DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). Diese Funktion wird aufgerufen, während des Ladens und Speichern des Steuerelementobjekts, speichert alle Eigenschaften, die mit einer Membervariablen gespeichert oder mit einer Membervariablen mit änderungsbenachrichtigung implementiert.  
  
 Die folgenden Themen behandeln die wichtigsten Probleme, die im Zusammenhang mit Serialisierung eines ActiveX-Steuerelements:  
  
-   Implementieren von `DoPropExchange` Funktion, um die Control-Objekt zu serialisieren  
  
-   [Anpassen des Serialisierungsprozesses](#_core_customizing_the_default_behavior_of_dopropexchange)  
  
-   [Implementieren der Versionsunterstützung](#_core_implementing_version_support)  
  
##  <a name="_core_implementing_the_dopropexchange_function"></a> Implementieren der DoPropExchange-Funktion  
 Wenn Sie dem ActiveX-Steuerelement-Assistenten verwenden, um das Projekt zu generieren, mehrere Standard-Handlerfunktionen automatisch hinzugefügt werden der Control-Klasse, die standardmäßige Implementierung des einschließlich [COleControl:: DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). Das folgende Beispiel zeigt den Code, mit dem ActiveX-Steuerelement-Assistenten erstellte Klassen hinzugefügt:  
  
 [!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]  
  
 Wenn Sie eine Eigenschaft dauerhaft zu machen möchten, ändern Sie `DoPropExchange` durch einen Aufruf der Eigenschaft Exchange-Funktion hinzufügen. Das folgende Beispiel veranschaulicht die Serialisierung einer benutzerdefinierten booleschen CircleShape-Eigenschaft, die, in denen die CircleShape-Eigenschaft den Standardwert hat **"true"**:  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]  
  
 Die folgende Tabelle enthält die möglichen Eigenschaft Exchange-Funktionen, die Sie verwenden können, um die Eigenschaften des Steuerelements zu serialisieren:  
  
|Exchange-Eigenschaftenfunktionen|Zweck|  
|---------------------------------|-------------|  
|**PX_Blob)**|Serialisiert ein Binary Large Object (BLOB) Data-Eigenschaft.|  
|**PX_Bool)**|Serialisiert eine Eigenschaft vom Typ Boolean.|  
|**PX_Color)**|Serialisiert eine Farbeigenschaft Typ an.|  
|**PX_Currency)**|Einen Typ serialisiert **CY** (Währung)-Eigenschaft.|  
|**PX_Double)**|Einen Typ serialisiert **doppelte** Eigenschaft.|  
|**PX_Font)**|Serialisiert eine Eigenschaft vom Typ Schriftart an.|  
|**PX_Float)**|Einen Typ serialisiert **"float"** Eigenschaft.|  
|**PX_IUnknown)**|Serialisiert eine Eigenschaft vom Typ `LPUNKNOWN`.|  
|**PX_Long)**|Einen Typ serialisiert **lange** Eigenschaft.|  
|**PX_Picture)**|Serialisiert ein Picture-Eigenschaft.|  
|**PX_Short)**|Einen Typ serialisiert **kurze** Eigenschaft.|  
|**PXstring)**|Einen Typ serialisiert `CString` Eigenschaft.|  
|**PX_ULong)**|Einen Typ serialisiert **ULONG** Eigenschaft.|  
|**PX_UShort)**|Einen Typ serialisiert **"ushort"** Eigenschaft.|  
  
 Weitere Informationen zu diesen Eigenschaft Exchange-Funktionen finden Sie unter [Persistenz der OLE-Steuerelemente](../mfc/reference/persistence-of-ole-controls.md) in der *MFC-Referenz*.  
  
##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a> Das Standardverhalten des DoPropExchange anpassen  
 Die standardmäßige Implementierung des **DoPropertyExchange** (wie im vorherigen Thema gezeigt) stellt einen Aufruf in eine Basisklasse `COleControl`. Serialisiert den Satz von Eigenschaften, die automatisch von unterstützt `COleControl`, die mehr Speicherplatz benötigt als serialisiert nur die benutzerdefinierten Eigenschaften des Steuerelements verwendet. Entfernen diesen Aufruf, kann das Objekt nur die Eigenschaften serialisiert werden, die Sie wichtige berücksichtigen. Beliebiger Systemeigenschaft-Status wurde das Steuerelement implementiert werden nicht serialisiert werden, beim Speichern oder laden das Steuerelementobjekt, es sei denn, Sie explizit hinzufügen **PX_** dafür aufruft.  
  
##  <a name="_core_implementing_version_support"></a> Implementieren der Versionsunterstützung  
 Versionsunterstützung ermöglicht eine überarbeitete ActiveX-Steuerelement zum Hinzufügen von neuer permanenter Eigenschaften und weiterhin in der Lage zu ermitteln und Laden des persistenten Status, die von einer früheren Version des Steuerelements erstellt. Um die Version des Steuerelements zur Verfügung stellen rufen Sie im Rahmen der persistenten Daten [COleControl:: ExchangeVersion](../mfc/reference/colecontrol-class.md#exchangeversion) in des Steuerelements `DoPropExchange` Funktion. Dieser Aufruf wird automatisch eingefügt, wenn das ActiveX-Steuerelement mit dem ActiveX-Steuerelement-Assistenten erstellt wurde. Es kann entfernt werden, wenn versionsunterstützung nicht benötigt wird. Die Kosten im Steuerelementgröße ist jedoch sehr klein (4 Bytes) für die Flexibilität, die Version unterstützt.  
  
 Wenn das Steuerelement nicht mit dem ActiveX-Steuerelement-Assistenten erstellt wurde, fügen Sie einen Aufruf von `COleControl::ExchangeVersion` durch Einfügen die folgende Zeile am Anfang der `DoPropExchange` Funktion (vor dem Aufruf von `COleControl::DoPropExchange`):  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 Sie können eine `DWORD` als Versionsnummer. Verwenden Sie die Projekte, die von der ActiveX-Steuerelement-Assistent generiert **standardmäßig _wVerMinor** und **_wVerMajor** als Standard. Hierbei handelt es sich um globale Konstanten in der Implementierungsdatei des ActiveX-Steuerelementklasse des Projekts definiert. Im übrigen Teil Ihrer `DoPropExchange` -Funktion, die Sie aufrufen können [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion) jederzeit aufrufen, um die Version abzurufen, Sie speichern oder abrufen.  
  
 Im folgenden Beispiel weist die Version 1 von diesem Beispielsteuerelement nur eine "ReleaseDate"-Eigenschaft. Version 2 Fügt eine Eigenschaft "OriginalDate" hinzu. Wenn Sie das Steuerelement beim Laden des persistenten Status aus der alten Version angewiesen wird, initialisiert er die Membervariable für die neue Eigenschaft auf einen Standardwert an.  
  
 [!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 Standardmäßig konvertiert"ein Steuerelement" alte Daten in das aktuelle Format. Z. B. wenn Version 2 eines Steuerelements Daten, die mit Version 1 gespeichert wurde lädt, wird es das Versionsformat 2 schreiben, wenn sie erneut gespeichert wird. Wenn Sie das Steuerelement zum Speichern von Daten in das letzte Format lesen soll, übergeben **"false"** als dritten Parameter beim Aufrufen von `ExchangeVersion`. Dieser dritte Parameter ist optional und wird **"true"** standardmäßig.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

