---
title: Compilerwarnung (Stufen 2 und 3) C4008 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4008
dev_langs:
- C++
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 0539a36dddf5bed1d7474f6456eb710bb0506ae4
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Compilerwarnung (Stufen 2 und 3) C4008
'Bezeichner': 'Attribut'-Attribut wird ignoriert  
  
 Der Compiler ignoriert die Attribute `__fastcall`, **static**oder **inline** für eine Funktion (Warnstufe 3) oder für Daten (Warnstufe 2).  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  `__fastcall`ein Attribut mit Daten.  
  
2.  Attribute**static** oder **inline** mit **main** -Funktion.
