---
title: Compilerfehler C2241 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2241
dev_langs:
- C++
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d1a4404d3f7e60adc2d8f9ff0c8ccb3d154b26d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2241"></a>Compilerfehler C2241
'Bezeichner': Memberzugriff ist eingeschränkt.  
  
 Der Code versucht, auf einen privaten oder geschützten Member zuzugreifen.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Ändern Sie die Zugriffsebene des Members.  
  
2.  Deklarieren Sie den Member als `friend` der zugreifenden Funktion.