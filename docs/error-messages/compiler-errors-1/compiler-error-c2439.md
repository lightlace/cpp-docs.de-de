---
title: Compilerfehler C2439 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2439
dev_langs:
- C++
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6aa5c0dcfd12be6979b0872f001bf0bf26a6e6e7
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2439"></a>Compilerfehler C2439
'Bezeichner': Member konnte nicht initialisiert werden  
  
 Eine Klasse, Struktur oder union-Member kann nicht initialisiert werden.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Versucht, eine indirekte Basisklasse der Klasse oder Struktur zu initialisieren.  
  
2.  Versucht, einen geerbten Member einer Klasse oder Struktur zu initialisieren. Ein geerbter Member muss vom Konstruktor der Klasse oder Struktur initialisiert werden.
