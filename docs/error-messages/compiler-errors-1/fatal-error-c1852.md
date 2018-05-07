---
title: Schwerwiegender Fehler C1852 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1852
dev_langs:
- C++
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d11160eea5e978a0c1ef67255d4e96b48fe2d101
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1852"></a>Schwerwiegender Fehler C1852
'Dateiname' ist keine gültige vorkompilierte Headerdatei.  
  
 Die Datei ist kein vorkompilierter Header.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Es wurde eine ungültige Datei mit **/Yu** oder **#pragma hdrstop**angegeben.  
  
2.  Wenn Sie keine andere Angabe vornehmen, nimmt der Compiler die Dateierweiterung PCH an.