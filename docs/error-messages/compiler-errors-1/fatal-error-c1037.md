---
title: Schwerwiegender Fehler C1037 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c1f358201b36b73e1db41f2f72e1f92deb44f368
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1037"></a>Schwerwiegender Fehler C1037
Objektdatei kann nicht geöffnet werden  
  
 Die durch [/Fo](../../build/reference/fo-object-file-name.md) angegebene Objektdatei kann nicht geöffnet werden.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Ungültiger Dateiname.  
  
2.  Es ist nicht genügend Speicher verfügbar, um die Datei zu öffnen.  
  
3.  Die Datei wird von einem anderen Prozess verwendet.  
  
4.  Eine schreibgeschützte Datei hat den gleichen Namen.  
  
 In Visual C++ .NET (Version 1300 des Compilers) liegt ein Fehler vor, der erfordert, dass das Benutzergebietsschema richtig festgelegt wird, wenn der Dateiname (oder der Verzeichnispfad zum Dateinamen) MBCS-Zeichen enthält. Das Festlegen des Systemgebietsschemas ist nicht ausreichend; das Benutzergebietsschema muss festgelegt werden, damit MBCS-Zeichen verarbeitet werden.
