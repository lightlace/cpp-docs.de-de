---
title: Warnung LNK4037 der Linkertools | Microsoft Docs
ms.custom: 
ms.date: 10/04/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4037
dev_langs:
- C++
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c93eab2faf81e4cd743eae4befa2f842c100589
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4037"></a>Linkertoolwarnung LNK4037

>"*Symbol*" ist nicht vorhanden; ignoriert

Der ergänzte Name *Symbol* konnte nicht sortiert werden, mithilfe der [/ORDER](../../build/reference/order-put-functions-in-order.md) option, da es in der Anwendung nicht gefunden werden konnte. Überprüfen Sie die Angabe von *Symbol* in der Antwortdatei Reihenfolge. Weitere Informationen finden Sie unter der [/Order (Reihenfolge von Funktionen Put)](../../build/reference/order-put-functions-in-order.md) (Linkeroption).

> [!NOTE]
> LINK kann nicht statische Funktionen sortieren, da statische Funktionsnamen nicht öffentliche Symbolnamen sind. Wenn **/ORDER** angegeben ist, wird diese linkerwarnung für jedes Symbol in der Reihenfolge Antwortdatei, die entweder eine statische generiert wird oder nicht gefunden.