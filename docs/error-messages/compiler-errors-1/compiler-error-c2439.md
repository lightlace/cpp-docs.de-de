---
title: Compilerfehler C2439 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2439
dev_langs:
- C++
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33bfe8ebf00850a54020b2a3f21159daf28b7224
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2439"></a>Compilerfehler C2439
'Bezeichner': Member konnte nicht initialisiert werden  
  
 Eine Klasse, Struktur oder union-Member kann nicht initialisiert werden.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Versucht, eine indirekte Basisklasse der Klasse oder Struktur zu initialisieren.  
  
2.  Versucht, einen geerbten Member einer Klasse oder Struktur zu initialisieren. Ein geerbter Member muss vom Konstruktor der Klasse oder Struktur initialisiert werden.