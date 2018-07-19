---
title: Warnung LNK4037 der Linkertools | Microsoft Docs
ms.custom: ''
ms.date: 10/04/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4037
dev_langs:
- C++
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b87f0a415d6ae7d282e29c2ca67fda043c2a901
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302434"
---
# <a name="linker-tools-warning-lnk4037"></a>Linkertoolwarnung LNK4037

>"*Symbol*" ist nicht vorhanden; ignoriert

Der ergänzte Name *Symbol* konnte nicht sortiert werden, mithilfe der [/ORDER](../../build/reference/order-put-functions-in-order.md) option, da es in der Anwendung nicht gefunden werden konnte. Überprüfen Sie die Angabe von *Symbol* in der Antwortdatei Reihenfolge. Weitere Informationen finden Sie unter der [/Order (Reihenfolge von Funktionen Put)](../../build/reference/order-put-functions-in-order.md) (Linkeroption).

> [!NOTE]
> LINK kann nicht statische Funktionen sortieren, da statische Funktionsnamen nicht öffentliche Symbolnamen sind. Wenn **/ORDER** angegeben ist, wird diese linkerwarnung für jedes Symbol in der Reihenfolge Antwortdatei, die entweder eine statische generiert wird oder nicht gefunden.