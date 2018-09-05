---
title: Verwenden von IDispEventSimpleImpl (ATL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventSimpleImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a47cef741e9db3237bbc9f6477cdf2863b38e4e3
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760369"
---
# <a name="using-idispeventsimpleimpl"></a>Verwenden von IDispEventSimpleImpl

Bei Verwendung `IDispEventSimpleImpl` zum Verarbeiten von Ereignissen, müssen Sie:

- Leiten Sie eine Klasse von [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md).

- Fügen Sie eine Senke-Event-Zuordnung zu einer Klasse hinzu.

- Definieren Sie [_ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md) Strukturen, die die Ereignisse beschreibt.

- Fügen Sie Einträge hinzu, um die Ereignissenke Zuordnung mithilfe der [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) Makro.

- Implementieren Sie die Methoden, die Sie bei der Verwendung von Interesse sind.

- Melden Sie an und die Ereignisquelle.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Behandeln der `DocumentChange` Ereignis ausgelöst wird, von Word **Anwendung** Objekt. Dieses Ereignis wird als eine Methode definiert, auf die `ApplicationEvents` Disp-Schnittstelle.

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

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]

Die einzige Informationen aus der Typbibliothek, die tatsächlich verwendeten in diesem Beispiel ist die CLSID des Worts `Application` -Objekt und die IID der `ApplicationEvents` Schnittstelle. Diese Informationen werden nur zum Zeitpunkt der Kompilierung verwendet.

Der folgende Code wird im Simple.h angezeigt. Der entsprechende Code wird durch Kommentare aufgeführt:

[!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]

Der folgende Code stammt aus Simple.cpp:

[!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]

## <a name="see-also"></a>Siehe auch

[Behandlung von Ereignissen](../atl/event-handling-and-atl.md)   
[ATLEventHandling-Beispiel](../visual-cpp-samples.md)

