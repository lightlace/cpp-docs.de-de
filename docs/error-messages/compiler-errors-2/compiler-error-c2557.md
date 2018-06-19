---
title: Compilerfehler C2557 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2557
dev_langs:
- C++
helpviewer_keywords:
- C2557
ms.assetid: 48a33d82-aa16-4658-b346-2311fcb39864
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5402cb98d2cf315861ccb27aad3233b3bd370f8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227407"
---
# <a name="compiler-error-c2557"></a>Compilerfehler C2557
"Bezeichner": Private und geschützte Member können nicht ohne Konstruktor initialisiert werden.  
  
 Nur Member und Freunde können einem privaten oder geschützten Member einen Wert zuweisen. Nicht öffentliche Member sollten im Klassenkonstruktor initialisiert werden.