---
title: Compilerfehler C2241 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2241
dev_langs:
- C++
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0625c4682ff44904ce166d370ec797c1d147ad02
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2241"></a>Compilerfehler C2241
'Bezeichner': Memberzugriff ist eingeschränkt.  
  
 Der Code versucht, auf einen privaten oder geschützten Member zuzugreifen.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Ändern Sie die Zugriffsebene des Members.  
  
2.  Deklarieren Sie den Member als `friend` der zugreifenden Funktion.
