---
title: Schwerwiegender Fehler C1037 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1037
dev_langs:
- C++
helpviewer_keywords:
- C1037
ms.assetid: 79103bca-ccfb-42e7-aef9-9b90c15b162f
caps.latest.revision: 7
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
ms.openlocfilehash: 892ce10f7d19266ce45d559ce35bc82946887c52
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1037"></a>Schwerwiegender Fehler C1037
Objektdatei kann nicht geöffnet werden  
  
 Durch angegebene Objektdatei [/Fo](../../build/reference/fo-object-file-name.md) kann nicht geöffnet werden.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Ungültiger Dateiname.  
  
2.  Es ist nicht genügend Speicher verfügbar, um die Datei zu öffnen.  
  
3.  Die Datei wird von einem anderen Prozess verwendet.  
  
4.  Eine schreibgeschützte Datei hat den gleichen Namen.  
  
 In Visual C++ .NET (Version 1300 des Compilers) liegt ein Fehler vor, der erfordert, dass das Benutzergebietsschema richtig festgelegt wird, wenn der Dateiname (oder der Verzeichnispfad zum Dateinamen) MBCS-Zeichen enthält. Das Festlegen des Systemgebietsschemas ist nicht ausreichend; das Benutzergebietsschema muss festgelegt werden, damit MBCS-Zeichen verarbeitet werden.
