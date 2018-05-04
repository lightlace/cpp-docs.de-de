---
title: Unterstützung von IDispEventImpl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 680396ae912cca5f19e87697e7de0033213cc963
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="supporting-idispeventimpl"></a>Unterstützung von IDispEventImpl
Die Vorlagenklasse [IDispEventImpl](../atl/reference/idispeventimpl-class.md) können verwendet werden, um zur Verbindung Punkt senken in Ihrer Klasse ATL-Unterstützung bereit. Connection Point Senke ermöglicht, Ihre Klasse zum Behandeln von Ereignissen aus externen COM-Objekten, das ausgelöst wird. Diese Verbindung Punkt senken werden mit einer Senke ereigniszuordnung bereitgestellt, die von Ihrer Klasse zugeordnet.  
  
 Um eine Verbindung zeigen eine Ereignissenke für Ihre Klasse ordnungsgemäß zu implementieren, müssen die folgenden Schritte ausgeführt werden:  
  
-   Importieren Sie für jedes Objekt externen Typbibliotheken  
  
-   Deklarieren der `IDispEventImpl` Schnittstellen  
  
-   Deklarieren Sie eine Senke ereigniszuordnung  
  
-   Melden Sie an und die Verbindungspunkte  
  
 Die Schritte zum Implementieren einer Connection Point Senke, die alle durch das Ändern der nur der Headerdatei (. h) der Klasse erreicht werden.  
  
## <a name="importing-the-type-libraries"></a>Importieren von Typbibliotheken  
 Für jedes externe Objekt, dessen Ereignisse Sie behandeln möchten, müssen Sie die Typbibliothek importieren. Dieser Schritt definiert die Ereignisse, die behandelt werden können und enthält Informationen, die verwendet wird, wenn die Senke ereigniszuordnung deklarieren. Die [#import](../preprocessor/hash-import-directive-cpp.md) -Direktive kann verwendet werden, um dies zu erreichen. Fügen Sie die erforderlichen `#import` Richtlinie Zeilen für jede Dispatchschnittstelle die Headerdatei (. h) der Klasse unterstützt.  
  
 Im folgende Beispiel wird die Typbibliothek, die von einer externen COM-Server importiert (`MSCAL.Calendar.7`):  
  
 [!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]  
  
> [!NOTE]
>  Sie benötigen ein separates `#import` -Anweisung für jede externe Typbibliothek, die Sie unterstützen.  
  
## <a name="declaring-the-idispeventimpl-interfaces"></a>Deklarieren Sie die IDispEventImpl-Schnittstellen  
 Nun, dass Sie die Typbibliotheken der einzelnen Verteilschnittstelle importiert haben, müssen Sie separate deklarieren `IDispEventImpl` Schnittstellen für jede externe Dispatchschnittstelle. Ändern Sie die Deklaration der Klasse durch Hinzufügen einer `IDispEventImpl` -Schnittstellendeklaration für jedes externe Objekt. Weitere Informationen zu den Parametern finden Sie unter [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
 Der folgende Code deklariert zwei Connection Point senken, für die `DCalendarEvents` -Schnittstelle, für die COM-Objekt, das von der Klasse implementiert `CMyCompositCtrl2`:  
  
 [!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]  
  
## <a name="declaring-an-event-sink-map"></a>Deklarieren Sie eine Senke Ereigniszuordnung  
 Damit die ereignisbenachrichtigungen von der ordnungsgemäßen Funktion behandelt werden kann muss Ihre Klasse jedes Ereignis zu seinem richtigen Ereignishandler weitergeleitet werden. Dies erfolgt durch Deklarieren einer Senke ereigniszuordnung.  
  
 ATL stellt mehrere Makros [BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map), [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map), und [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex), erleichtern diese Zuordnung. Das Standardformat lautet wie folgt:  
  
 `BEGIN_SINK_MAP(comClass)`  
  
 `SINK_ENTRY_EX(id, iid, dispid, func)`  
  
 `. . . //additional external event entries`  
  
 `END_SINK_MAP()`  
  
 Das folgende Beispiel deklariert ein Ereignissenke Karte mit zwei Ereignishandler:  
  
 [!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]  
  
 Die Implementierung ist fast abgeschlossen. Der letzte Schritt betrifft das anmelden und Abmelden der externen Schnittstellen.  
  
## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>Anmelden und Abmelden der IDispEventImpl-Schnittstellen  
 Der letzte Schritt besteht eine Methode, die (alle Verbindungspunkte senkereigniszuordnung oder wird) zu den entsprechenden Zeitpunkten implementieren. Diese Anmeldung muss ausgeführt werden, bevor die Kommunikation zwischen den externen Clients und dem Objekt durchgeführt werden kann. Bevor das Objekt sichtbar ist, wird jede externe Dispatchschnittstelle, die vom Objekt unterstützte für Ausgangsschnittstellen abgefragt. Eine Verbindung hergestellt und ein Verweis auf die Ausgangsschnittstelle wird verwendet, um Ereignisse aus dem Objekt zu behandeln. Diese Prozedur spricht man von "Anmelden".  
  
 Nachdem das Objekt mit den externen Schnittstellen abgeschlossen ist, sollte die Ausgangsschnittstellen benachrichtigt werden, dass sie nicht mehr von der Klasse verwendet werden. Dieser Prozess wird als "Abmelden" bezeichnet  
  
 Aufgrund der eindeutigen Natur von COM-Objekten variiert dieses Verfahren im Detail und Ausführung zwischen Implementierungen. Diese Details sind nicht Gegenstand dieses Themas und nicht eingegangen.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)

