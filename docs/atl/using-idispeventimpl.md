---
title: Verwenden von IDispEventImpl (ATL) | Microsoft-Dokumentation
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
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d28a9a8bad8ced772d5c698e76d3d08f09c8db2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066473"
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

Das Beispiel stammt aus dem [ATLEventHandling-Beispiel](../visual-cpp-samples.md).

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
[ATLEventHandling-Beispiel](../visual-cpp-samples.md)

