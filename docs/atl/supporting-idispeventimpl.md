---
title: Unterstützen von IDispEventImpl
ms.date: 11/04/2016
f1_keywords:
- IDispEventImpl
helpviewer_keywords:
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
ms.openlocfilehash: fcc3be5d905bf3f5680902e2f480472c6251aa7f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273815"
---
# <a name="supporting-idispeventimpl"></a>Unterstützen von IDispEventImpl

Die Vorlagenklasse [IDispEventImpl](../atl/reference/idispeventimpl-class.md) kann verwendet werden, um Unterstützung für die Verbindung Punkt senken in der ATL-Klasse bereitzustellen. Connection Point Senke können Ihre Klasse zum Behandeln von Ereignissen, die von externen COM-Objekten ausgelöst. Diese Verbindung Punkt senken werden mit einer Senke ereigniszuordnung bereitgestellt, die von Ihrer Klasse zugeordnet.

Um eine Verbindung Punkt Senke für die Klasse ordnungsgemäß zu implementieren, müssen die folgenden Schritte ausgeführt werden:

- Importieren Sie die Typbibliotheken für die einzelnen externen Objekte

- Deklarieren Sie die `IDispEventImpl` Schnittstellen

- Deklarieren Sie eine Senke ereigniszuordnung

- Melden Sie an und die Verbindungspunkte

Die Schritte zum Implementieren einer Connection Point-Senke werden alle erreicht, indem nur die Header-Datei (. h) der Klasse ändern.

## <a name="importing-the-type-libraries"></a>Importieren von Typbibliotheken

Für jedes externe-Objekt, dessen Ereignisse, die Sie behandeln möchten, müssen Sie die Bibliothek importieren. Dieser Schritt definiert die Ereignisse, die verarbeitet werden können, und enthält Informationen, die verwendet wird, wenn die Senke ereigniszuordnung deklarieren. Die [#import](../preprocessor/hash-import-directive-cpp.md) -Direktive kann verwendet werden, um dies zu erreichen. Fügen Sie die erforderlichen `#import` -Direktive Zeilen für jede Dispatchschnittstelle, die Sie in der Headerdatei (. h) der Klasse unterstützt.

Das folgende Beispiel importiert die Typbibliothek eines externen COM-Servers (`MSCAL.Calendar.7`):

[!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]

> [!NOTE]
>  Sie benötigen eine Separate `#import` -Anweisung für jede externe Typbibliothek, die Sie unterstützen.

## <a name="declaring-the-idispeventimpl-interfaces"></a>Deklarieren Sie die Schnittstellen von IDispEventImpl

Nachdem Sie die Typbibliotheken der einzelnen Dispatchschnittstelle importiert haben, müssen Sie separate deklarieren `IDispEventImpl` Schnittstellen für die einzelnen externen Dispatch-Schnittstellen. Ändern Sie die Deklaration der Klasse, durch das Hinzufügen einer `IDispEventImpl` Schnittstellendeklaration für jedes externe Objekt. Weitere Informationen zu den Parametern finden Sie unter [IDispEventImpl](../atl/reference/idispeventimpl-class.md).

Der folgende Code deklariert zwei Connection Point senken, für die `DCalendarEvents` Schnittstelle, für das COM-Objekt, das von der Klasse implementiert `CMyCompositCtrl2`:

[!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]

## <a name="declaring-an-event-sink-map"></a>Deklarieren Sie eine Senke Ereigniszuordnung

Damit die ereignisbenachrichtigungen von der ordnungsgemäßen Funktion behandelt werden kann muss die Klasse jedes Ereignis an die richtigen Handler weitergeleitet werden. Dies erfolgt durch eine Senke ereigniszuordnung deklarieren.

ATL stellt mehrere Makros [BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map), [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map), und [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex), erleichtern diese Zuordnung. Das Standardformat lautet wie folgt aus:

```cpp
BEGIN_SINK_MAP(comClass)
  SINK_ENTRY_EX(id, iid, dispid, func)
  . . . //additional external event entries
END_SINK_MAP()
```

Das folgende Beispiel deklariert eine Senke ereigniszuordnung mit zwei Ereignishandler:

[!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]

Die Implementierung ist fast abgeschlossen. Der letzte Schritt betrifft das anmelden und Abmelden von externen Schnittstellen.

## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>Anmelden und Abmelden von IDispEventImpl-Schnittstellen

Der letzte Schritt ist eine Methode, die alle Verbindungspunkte empfehlen Sie (oder abzumelden) wird zu den richtigen Zeitpunkten implementieren. Diese Anmeldung muss ausgeführt werden, bevor die Kommunikation zwischen externen Clients und das Objekt durchgeführt werden kann. Bevor das Objekt angezeigt wird, wird jede externe Dispatchschnittstelle, die vom Objekt unterstützte für Ausgangsschnittstellen abgefragt. Eine Verbindung hergestellt wird, und ein Verweis auf die Ausgangsschnittstelle wird verwendet, um Ereignisse aus dem Objekt zu behandeln. Dieses Verfahren wird als "Anmelden" bezeichnet

Nachdem das Objekt mit den externen Schnittstellen fertig ist, sollte die Ausgangsschnittstellen benachrichtigt werden, dass sie von Ihrer Klasse nicht mehr verwendet werden. Dieser Prozess wird als "Abmelden". um bezeichnet.

Aufgrund der eindeutigen Natur von COM-Objekten variiert diese Prozedur im Detail und Ausführung zwischen Implementierungen. Diese Informationen werden über den Rahmen dieses Themas hinaus und sind nicht Gegenstand.

## <a name="see-also"></a>Siehe auch

[Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)
