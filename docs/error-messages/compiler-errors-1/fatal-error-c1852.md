---
title: Schwerwiegender Fehler C1852 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cd7168c6ffa653af54404bf81cdc4d308a76783a
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1852"></a>Schwerwiegender Fehler C1852
'Dateiname' ist keine gültige vorkompilierte Headerdatei.  
  
 Die Datei ist kein vorkompilierter Header.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Es wurde eine ungültige Datei mit **/Yu** oder **#pragma hdrstop**angegeben.  
  
2.  Wenn Sie keine andere Angabe vornehmen, nimmt der Compiler die Dateierweiterung PCH an.
