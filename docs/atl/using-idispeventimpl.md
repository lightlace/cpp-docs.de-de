---
title: Verwenden von IDispEventImpl (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
ms.openlocfilehash: c532164788d359c7834759de01407d49c19463ca
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769328"
---
# <a name="using-idispeventimpl"></a>Verwenden von IDispEventImpl

Bei Verwendung `IDispEventImpl` zum Verarbeiten von Ereignissen, müssen Sie:

- Leiten Sie eine Klasse von [IDispEventImpl](../atl/reference/idispeventimpl-class.md).

- Fügen Sie eine Senke-Event-Zuordnung zu einer Klasse hinzu.

- Fügen Sie Einträge hinzu, um die Ereignissenke Zuordnung mithilfe der [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) oder [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) Makro.

- Implementieren Sie die Methoden, die Sie bei der Verwendung von Interesse sind.

- Melden Sie an und die Ereignisquelle.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie behandelt die `DocumentChange` Ereignis ausgelöst wird, von Word **Anwendung** Objekt. Dieses Ereignis wird als eine Methode definiert, auf die `ApplicationEvents` Disp-Schnittstelle.

Das Beispiel stammt aus dem [ATLEventHandling-Beispiel](../overview/visual-cpp-samples.md).

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

Im Beispiel wird `#import` auf die erforderlichen Header-Dateien von Word Typbibliothek zu generieren. Wenn Sie dieses Beispiel mit anderen Versionen von Word verwenden möchten, müssen Sie die richtige Mso-Dll-Datei angeben. Beispielsweise Office 2000 stellt mso9.dll und OfficeXP mso.dll bereit. Dieser Code wird von "stdafx.h" vereinfacht:

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

Der folgende Code wird im NotSoSimple.h angezeigt. Der entsprechende Code wird durch Kommentare aufgeführt:

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>Siehe auch

[Ereignisbehandlung](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling-Beispiel](../overview/visual-cpp-samples.md)
