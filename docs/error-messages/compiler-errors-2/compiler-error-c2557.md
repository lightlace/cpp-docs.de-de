---
title: Compilerfehler C2557 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2557
dev_langs:
- C++
helpviewer_keywords:
- C2557
ms.assetid: 48a33d82-aa16-4658-b346-2311fcb39864
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 044bfcaeb70a2a1ab3b4a349bf9019879210e82b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2557"></a>Compilerfehler C2557
"Bezeichner": Private und geschützte Member können nicht ohne Konstruktor initialisiert werden.  
  
 Nur Member und Freunde können einem privaten oder geschützten Member einen Wert zuweisen. Nicht öffentliche Member sollten im Klassenkonstruktor initialisiert werden.