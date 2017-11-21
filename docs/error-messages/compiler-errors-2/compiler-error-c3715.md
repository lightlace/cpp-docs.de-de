---
title: Compilerfehler C3715 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3715
dev_langs: C++
helpviewer_keywords: C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0fcfe83ada2c55540562fc17189d693675326c81
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3715"></a>Compilerfehler C3715
"Zeiger": muss ein Zeiger auf "Klasse"  
  
 Einen Zeiger im angegebenen [__hook](../../cpp/hook.md) oder [__unhook](../../cpp/unhook.md) zeigen, die nicht auf eine gültige Klasse. Zum Beheben dieses Fehlers sicher, dass Ihre `__hook` und `__unhook` Aufrufe geben Zeiger zu den gültigen Klassen.