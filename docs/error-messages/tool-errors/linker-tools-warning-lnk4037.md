---
title: Linkertoolwarnung LNK4037
ms.date: 10/04/2017
f1_keywords:
- LNK4037
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
ms.openlocfilehash: 9a8121617e622fc12efe5bd26aac23faf2530f24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410303"
---
# <a name="linker-tools-warning-lnk4037"></a>Linkertoolwarnung LNK4037

>"*Symbol*' ist nicht vorhanden; wird ignoriert.

Der ergänzte Name *Symbol* konnte nicht sortiert werden, mithilfe der [/ORDER](../../build/reference/order-put-functions-in-order.md) -Option fest, da es in das Programm nicht gefunden werden konnte. Überprüfen Sie die Angabe von *Symbol* in der Order-Antwortdatei. Weitere Informationen finden Sie unter den [/Order (Reihenfolge von Funktionen)](../../build/reference/order-put-functions-in-order.md) -Linkeroption.

> [!NOTE]
> LINK kann nicht statische Funktionen sortieren, da statische Funktionsnamen nicht öffentlichen Symbolnamen sind. Wenn **/ORDER** angegeben wird, diese zu unterdrückenden linkerwarnungen generiert für jedes Symbol in der Order-Antwortdatei, die entweder statisch sind oder nicht gefunden.