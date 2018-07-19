---
title: Linkertoolwarnung Lnk4219 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4219
dev_langs:
- C++
helpviewer_keywords:
- LNK4219
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59cb7376957b7985b7ae2335ea472171d490ff42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301134"
---
# <a name="linker-tools-warning-lnk4219"></a>Linkertoolwarnung LNK4219
Fixup Namen Fixup-Überlauf. Ziel "Symbolname Target" ist außerhalb des gültigen Bereichs, Thunk  
  
 Der Linker eingefügt einen Thunk in einer Situation, in dem die Adresse bzw. den Offset konnte nicht in die angegebene Anweisung nicht finden, da das Zielsymbol zu weit von der Anweisung Speicherort ist.  
  
 Möglicherweise möchten Sie das Bild neu anordnen (mithilfe der [/ORDER](../../build/reference/order-put-functions-in-order.md) option, z. B.), die zusätzliche Dereferenzierungsebene zu vermeiden.