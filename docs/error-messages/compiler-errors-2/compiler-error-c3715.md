---
title: Compilerfehler C3715 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3715
dev_langs:
- C++
helpviewer_keywords:
- C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9412592ac177fb49f065975db469c9f77b98e8c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265895"
---
# <a name="compiler-error-c3715"></a>Compilerfehler C3715
"Zeiger": muss ein Zeiger auf "Klasse"  
  
 Einen Zeiger im angegebenen [__hook](../../cpp/hook.md) oder [__unhook](../../cpp/unhook.md) zeigen, die nicht auf eine gültige Klasse. Zum Beheben dieses Fehlers sicher, dass Ihre `__hook` und `__unhook` Aufrufe geben Zeiger zu den gültigen Klassen.