---
title: Compilerfehler C2439 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2439
dev_langs: C++
helpviewer_keywords: C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 79b6ef4b6182a525bb8c8fc5e7e9fc7bd541f870
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2439"></a>Compilerfehler C2439
'Bezeichner': Member konnte nicht initialisiert werden  
  
 Eine Klasse, Struktur oder union-Member kann nicht initialisiert werden.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Versucht, eine indirekte Basisklasse der Klasse oder Struktur zu initialisieren.  
  
2.  Versucht, einen geerbten Member einer Klasse oder Struktur zu initialisieren. Ein geerbter Member muss vom Konstruktor der Klasse oder Struktur initialisiert werden.