---
title: 'MFC-ActiveX-Steuerelemente: Serialisierung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/12/2018
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
ms.openlocfilehash: 3be523feaacb403076f2c066943ca55ace958dce
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401836"
---
# <a name="mfc-activex-controls-serializing"></a>MFC-ActiveX-Steuerelemente: Serialisierung

In diesem Artikel wird erläutert, wie ein ActiveX-Steuerelement serialisiert wird. Serialisierung wird die Variable gelesen oder auf ein persistentes Speichermedium, z. B. eine Datenträgerdatei geschrieben. Die Microsoft Foundation Class (MFC)-Bibliothek bietet integrierte Unterstützung für die Serialisierung in Klasse `CObject`. `COleControl` Diese Unterstützung für ActiveX-Steuerelemente durch die Verwendung einer Eigenschaft Austauschmechanismus erweitert wird.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen über moderne Technologien, die ActiveX Ersetzen eines finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Serialisierung für ActiveX-Steuerelementen wird durch Überschreiben implementiert [COleControl:: DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). Dieser Funktion aufgerufen, die beim Laden und Speichern des Steuerelementobjekts, speichert alle Eigenschaften, die mit einer Membervariablen oder einer Membervariablen änderungsbenachrichtigung implementiert.

In den folgenden Themen behandeln die wichtigsten Probleme im Zusammenhang mit Serialisierung ein ActiveX-Steuerelement:

- Implementieren von `DoPropExchange` Funktion, um Ihr Steuerelementobjekt zu serialisieren

- [Anpassen des Serialisierungsprozesses](#_core_customizing_the_default_behavior_of_dopropexchange)

- [Implementieren der Versionsunterstützung von](#_core_implementing_version_support)

##  <a name="_core_implementing_the_dopropexchange_function"></a> Implementieren der DoPropExchange-Funktion

Wenn Sie den ActiveX-Steuerelement-Assistenten verwenden, um das Projekt zu generieren, mehrere Funktionen der Standard-Handler werden automatisch hinzugefügt die Control-Klasse, die standardmäßige Implementierung des einschließlich [COleControl:: DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). Das folgende Beispiel zeigt den Code, der mit dem ActiveX-Steuerelement-Assistenten erstellten Klassen hinzugefügt:

[!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]

Wenn Sie eine Eigenschaft persistent machen möchten, ändern Sie `DoPropExchange` durch Hinzufügen eines Aufrufs an die Exchange-Funktion. Das folgende Beispiel veranschaulicht die Serialisierung einer benutzerdefinierten booleschen CircleShape-Eigenschaft, die, in denen die CircleShape-Eigenschaft den Standardwert hat **"true"**:

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]

Die folgende Tabelle enthält die möglichen Eigenschaft Exchange-Funktionen, die Sie verwenden können, um die Eigenschaften des Steuerelements zu serialisieren:

|Exchange-Eigenschaftenfunktionen|Zweck|
|---------------------------------|-------------|
|**PX_Blob)**|Serialisiert ein Binary Large Object (BLOB) Data-Eigenschaft.|
|**PX_Bool)**|Serialisiert eine Eigenschaft vom Typ Boolean.|
|**PX_Color)**|Serialisiert die Color-Eigenschaft eines Typs.|
|**PX_Currency)**|Einen Typ serialisiert **CY** (Währung)-Eigenschaft.|
|**PX_Double)**|Einen Typ serialisiert **doppelte** Eigenschaft.|
|**PX_Font)**|Serialisiert eine Schriftart-Type-Eigenschaft.|
|**PX_Float)**|Einen Typ serialisiert **"float"** Eigenschaft.|
|**PX_IUnknown)**|Serialisiert eine Eigenschaft des Typs `LPUNKNOWN`.|
|**PX_Long)**|Einen Typ serialisiert **lange** Eigenschaft.|
|**PX_Picture)**|Serialisiert eine Bildeigenschaft-Typ.|
|**PX_Short)**|Einen Typ serialisiert **kurze** Eigenschaft.|
|**PXstring)**|Einen Typ serialisiert `CString` Eigenschaft.|
|**PX_ULong)**|Einen Typ serialisiert **ULONG** Eigenschaft.|
|**PX_UShort)**|Einen Typ serialisiert **USHORT** Eigenschaft.|

Weitere Informationen zu dieser Eigenschaft Exchange-Funktionen, finden Sie unter [Persistenz der OLE-Steuerelemente](../mfc/reference/persistence-of-ole-controls.md) in die *MFC-Referenz*.

##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a> Das Standardverhalten des DoPropExchange anpassen

Die standardmäßige Implementierung des `DoPropertyExchange` (wie im vorherigen Thema dargestellt) stellt einen Aufruf in eine Basisklasse `COleControl`. Serialisiert den Satz von Eigenschaften, die automatisch von unterstützten `COleControl`, die mehr Speicherplatz als serialisieren nur die benutzerdefinierten Eigenschaften des Steuerelements verwendet. Entfernen diesen Aufruf können das Objekt nur die Eigenschaften serialisiert werden, die Sie für wichtig halten. Systemeigenschaft Zustände hat das Steuerelement implementiert werden nicht serialisiert werden, beim Speichern oder laden das Steuerelementobjekt, es sei denn, Sie explizit hinzufügen **PX_** für sie aufruft.

##  <a name="_core_implementing_version_support"></a> Implementieren der Versionsunterstützung von

Versionsunterstützung ermöglicht eine überarbeitete ActiveX-Steuerelement zum Hinzufügen von neuer dauerhafte Eigenschaften und immer noch in der Lage zu erkennen und zu Laden des persistenten Status, die von einer früheren Version des Steuerelements erstellt. Zum Verfügbarmachen eines Steuerelements-Version als Teil der persistenten Daten, rufen Sie [COleControl:: ExchangeVersion](../mfc/reference/colecontrol-class.md#exchangeversion) in des Steuerelements `DoPropExchange` Funktion. Dieser Aufruf wird automatisch eingefügt, wenn das ActiveX-Steuerelement mit dem ActiveX-Steuerelement-Assistenten erstellt wurde. Er kann entfernt werden, wenn versionsunterstützung nicht erforderlich ist. Die Kosten in der Größe des Steuerelements ist jedoch sehr klein (4 Bytes), die mehr Flexibilität, die versionsunterstützung bietet.

Wenn das Steuerelement nicht mit dem ActiveX-Steuerelement-Assistenten erstellt wurde, fügen Sie einen Aufruf von `COleControl::ExchangeVersion` durch Einfügen von die folgende Zeile am Anfang Ihrer `DoPropExchange` Funktion (vor dem Aufruf von `COleControl::DoPropExchange`):

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

Sie können beliebige verwenden **DWORD** als Versionsnummer. Verwenden Sie die Projekte, die von der ActiveX-Steuerelement-Assistent generiert `_wVerMinor` und `_wVerMajor` als Standard. Hierbei handelt es sich um globale Konstanten in der Implementierungsdatei des ActiveX-Steuerelementklasse des Projekts definiert. Im übrigen Ihre `DoPropExchange` -Funktion, die Sie aufrufen können [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion) zu einem beliebigen Zeitpunkt aus, um die Version abzurufen, Sie speichern oder abrufen.

Im folgenden Beispiel hat die Version 1 des Steuerelements Beispiel nur eine "ReleaseDate"-Eigenschaft. Version 2 Fügt eine Eigenschaft "OriginalDate" hinzu. Wenn Sie das Steuerelement beim Laden des persistenten Status aus der alten Version angewiesen wird, initialisiert er die Membervariable für die neue Eigenschaft auf einen Standardwert an.

[!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

In der Standardeinstellung konvertiert"ein Steuerelement" alte Daten in das aktuelle Format. Z. B. wenn Version 2 eines Steuerelements Daten geladen wurden, die mit der Version 1 gespeichert wurde, wird er der 2-Versionsformat schreiben, wenn es noch Mal gespeichert wird. Wenn Sie das Steuerelement, das Daten in den letzten Lesevorgang von Format speichern möchten, übergeben Sie **"false"** als dritten Parameter beim Aufrufen von `ExchangeVersion`. Dieser dritte Parameter ist optional und ist **"true"** standardmäßig.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

