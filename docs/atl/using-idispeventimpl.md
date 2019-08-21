---
title: Verwenden von IDispEventImpl (ATL)
ms.date: 08/19/2019
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
ms.openlocfilehash: 9684781ba99d96e2c58d450ee0ff892374e33aef
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630599"
---
# <a name="using-idispeventimpl"></a>Verwenden von IDispEventImpl

Wenn Sie `IDispEventImpl` verwenden, um Ereignisse zu behandeln, müssen Sie folgende Schritte ausführen:

- Leiten Sie die Klasse von [IDispEventImpl](../atl/reference/idispeventimpl-class.md)ab.

- Fügen Sie der Klasse eine Ereignis Senke-Zuordnung hinzu.

- Fügen Sie mit dem [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) -oder [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) -Makro der Ereignis Senk Karte Einträge hinzu.

- Implementieren Sie die Methoden, die Sie behandeln möchten.

- Informieren Sie sich, und deaktivieren Sie die Ereignis Quelle.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie das `DocumentChange` -Ereignis behandelt wird, das von Word- **Anwendungs** Objekt ausgelöst wird. Dieses Ereignis ist als Methode für die `ApplicationEvents` dispinterface-Methode definiert.

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

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

Der folgende Code wird in "notsosimple. h" angezeigt. Der relevante Code wird in Kommentaren angegeben:

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>Siehe auch

[Ereignisbehandlung](../atl/event-handling-and-atl.md)<br/>
[Beispiel für "atleventhandelt"](../overview/visual-cpp-samples.md)
