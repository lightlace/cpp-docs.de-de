---
title: Asynchrone Moniker im Internet
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX controls [MFC], asynchronous
- MFC, asynchronous monikers
- asynchronous monikers [MFC]
- Web applications [MFC], asynchronous
- downloading Internet resources and asynchronous monikers
- optimization [MFC], asynchronous downloading across Internet
- Internet [MFC], asynchronous downloading
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
ms.openlocfilehash: e7a7ea51bca134e965747db8aac7f8a62822c9eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165839"
---
# <a name="asynchronous-monikers-on-the-internet"></a>Asynchrone Moniker im Internet

Im Internet werden neue Ansätze zum Anwendungsentwurf aufgrund der langsamen Netzwerkzugriff erfordert. Anwendungen sollten Netzwerkzugriff asynchron, um zu vermeiden, treten der Benutzeroberfläche ausführen. Die MFC-Klasse [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) asynchronen Unterstützung für das Herunterladen von Dateien enthält.

Mit asynchronen Monikern können Sie die COM-Anwendung asynchron über das Internet herunterladen und Bereitstellen von progressives Rendering große Objekte wie Bitmaps und VRML Objekte erweitern. Asynchrone Moniker ermöglichen eine ActiveX-Steuerelementeigenschaft oder eine Datei im Internet heruntergeladen werden, ohne dass Sie die Antwort auf die Benutzeroberfläche blockiert.

## <a name="advantages-of-asynchronous-monikers"></a>Vorteile der asynchronen Monikern

Sie können asynchrone Moniker zu verwenden:

- Herunterladen Sie Code und Dateien, ohne zu blockieren.

- Downloaden von Eigenschaften in ActiveX-Steuerelemente ohne zu blockieren.

- Empfang von Benachrichtigungen der Download wird ausgeführt.

- Nachverfolgen des Status "und" Status "bereit" Informationen ".

- Geben Sie Statusinformationen an den Benutzer ausgeführt.

- Ermöglicht dem Benutzer einen Download jederzeit abbrechen.

## <a name="mfc-classes-for-asynchronous-monikers"></a>MFC-Klassen für den asynchronen Monikern

[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) ergibt sich aus [CMonikerFile](../mfc/reference/cmonikerfile-class.md), die wiederum von abgeleitet ist [COleStreamFile](../mfc/reference/colestreamfile-class.md). Ein `COleStreamFile` Objekt, das einen Stream von Daten; einen `CMonikerFile` -Objekt verwendet einen `IMoniker` zum Abrufen der Daten, und ein `CAsyncMonikerFile` Objekt erfolgt asynchron.

Asynchrone Moniker werden in erster Linie in internetfähige Anwendungen und ActiveX-Steuerelemente verwendet, um eine reaktionsfähige Benutzeroberfläche während der Übertragung von Dateien bereitzustellen. Ein gutes Beispiel hierfür ist die Verwendung von [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md) zum Bereitstellen von asynchroner Eigenschaften für ActiveX-Steuerelemente.

## <a name="mfc-classes-for-data-paths-in-activex-controls"></a>MFC-Klassen für die Datenpfade in ActiveX-Steuerelementen

Die MFC-Klassen `CDataPathProperty` und [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) implementieren Sie die Eigenschaften von ActiveX-Steuerelemente, die asynchron geladen werden können. Asynchrone Eigenschaften werden nach der Initiierung der synchronen geladen. Asynchrone ActiveX-Steuerelemente aufrufen wiederholt einen Rückruf, um die Verfügbarkeit neuer Daten während einer langwierigen Eigenschaft Exchange-Vorgangs anzugeben.

`CDataPathProperty` wird von `CAsyncMonikerFile` abgeleitet. `CCachedDataPathProperty` wird von `CDataPathProperty` abgeleitet. Um die asynchrone Eigenschaften in der ActiveX-Steuerelemente zu implementieren, leiten Sie eine Klasse von `CDataPathProperty` oder `CCachedDataPathProperty`, und überschreiben [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) und andere Benachrichtigungen Sie empfangen möchten.

#### <a name="to-download-a-file-using-asynchronous-monikers"></a>Zum Herunterladen einer Datei, die mithilfe von asynchroner Monikern

1. Deklarieren Sie eine Klasse, die von abgeleiteten [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).

1. Außer Kraft setzen [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) zum Anzeigen der Daten.

1. Überschreiben Sie die anderen Memberfunktionen, z. B. [OnProgress](../mfc/reference/casyncmonikerfile-class.md#onprogress), [OnStartBinding](../mfc/reference/casyncmonikerfile-class.md#onstartbinding), und [OnStopBinding](../mfc/reference/casyncmonikerfile-class.md#onstopbinding).

1. Deklarieren Sie eine Instanz dieser Klasse und verwenden sie zum Öffnen von URLs.

Weitere Informationen zum Herunterladen von asynchron in einem ActiveX-Steuerelement, finden Sie unter [ActiveX-Steuerelemente für das Internet](../mfc/activex-controls-on-the-internet.md).

## <a name="see-also"></a>Siehe auch

[MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)<br/>
[Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)
