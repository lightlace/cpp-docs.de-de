---
title: Verwenden von IDispEventSimpleImpl (ATL)
ms.date: 08/19/2019
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
ms.openlocfilehash: 8a5e64093d2687efc6c6c5e9b0ce89402d2b99a4
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630585"
---
# <a name="using-idispeventsimpleimpl"></a>Verwenden von IDispEventSimpleImpl

Wenn Sie `IDispEventSimpleImpl` verwenden, um Ereignisse zu behandeln, müssen Sie folgende Schritte ausführen:

- Leiten Sie die Klasse von [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)ab.

- Fügen Sie der Klasse eine Ereignis Senke-Zuordnung hinzu.

- Definieren von [_ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md) -Strukturen, die die Ereignisse beschreiben.

- Fügen Sie der Ereignis Senke mithilfe des [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) -Makros Einträge hinzu.

- Implementieren Sie die Methoden, die Sie behandeln möchten.

- Informieren Sie sich, und deaktivieren Sie die Ereignis Quelle.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie das Ereignis `DocumentChange` behandelt wird, das von Word- **Anwendungs** Objekt ausgelöst wird. Dieses Ereignis ist als Methode für die `ApplicationEvents` dispinterface-Methode definiert.

Das Beispiel ist aus dem Beispiel " [atleventhandelt](../overview/visual-cpp-samples.md)".

```cpp
[ uuid(000209F7-0000-0000-C000-000000000046), hidden ]
dispinterface ApplicationEvents {
properties:
methods:
    [id(0x00000001), restricted, hidden]
    void Startup();

    [id(0x00000002)]
    void Quit();

    [id(0x00000003)]
    void DocumentChange();
};
```

Im Beispiel wird `#import` verwendet, um die erforderlichen Header Dateien aus der Typbibliothek von Word zu generieren. Wenn Sie dieses Beispiel mit anderen Versionen von Word verwenden möchten, müssen Sie die richtige MSO-DLL-Datei angeben. Beispielsweise stellt Office 2000 die Datei mso9. dll bereit, und OFFICEXP stellt mso. dll bereit. Dieser Code wird von " *PCH. h* " (*stdafx. h* in Visual Studio 2017 und früher) vereinfacht:

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]

Die einzigen Informationen aus der Typbibliothek, die in diesem Beispiel tatsächlich verwendet wird, sind die CLSID des Word `Application` -Objekts und die IID `ApplicationEvents` der Schnittstelle. Diese Informationen werden nur zum Zeitpunkt der Kompilierung verwendet.

Der folgende Code wird in "Simple. h" angezeigt. Der relevante Code wird in Kommentaren angegeben:

[!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]

Der folgende Code ist von Simple. cpp:

[!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]

## <a name="see-also"></a>Siehe auch

[Ereignisbehandlung](../atl/event-handling-and-atl.md)<br/>
[Beispiel für "atleventhandelt"](../overview/visual-cpp-samples.md)
