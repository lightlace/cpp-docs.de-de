---
title: Schwerwiegender Fehler C1852 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1852
dev_langs:
- C++
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
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
ms.openlocfilehash: f3e2b190ed3ec30c429bded2b6b695e1838cd078
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1852"></a>Schwerwiegender Fehler C1852
'Dateiname' ist keine gültige vorkompilierte Headerdatei.  
  
 Die Datei ist kein vorkompilierter Header.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Es wurde eine ungültige Datei mit **/Yu** oder **#pragma hdrstop**angegeben.  
  
2.  Wenn Sie keine andere Angabe vornehmen, nimmt der Compiler die Dateierweiterung PCH an.
