---
title: "Laufzeitfehlerüberprüfung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 3c1955bece0c8cdadb4a151ee06fa006402666a4
ms.openlocfilehash: 3aa56b70b02500998665289e69480570cfa39166
ms.contentlocale: de-de
ms.lasthandoff: 06/08/2017

---
# <a name="run-time-error-checking"></a>Laufzeitfehlerüberprüfung
Die C-Laufzeitbibliothek enthält die Funktionen, die Laufzeitfehlerüberprüfungen (Run-Time Error Checks, RTC) unterstützen. Mit der Laufzeitfehlerüberprüfung können Sie Ihr Programm so erstellen, dass bestimmte Arten von Laufzeitfehlern gemeldet werden. Sie geben an, welche Arten von Fehlern gemeldet werden sollen und wie die Meldung erfolgen soll. Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von systemeigenen Laufzeitprüfungen](/visualstudio/debugger/how-to-use-native-run-time-checks).  
  
 Verwenden Sie die folgenden Funktionen, um die Art und Weise anzupassen, in der Ihr Programm die Laufzeitfehlerüberprüfung ausführt.  
  
### <a name="run-time-error-checking-functions"></a>Funktionen der Laufzeitfehlerüberprüfung  
  
|Funktion|Verwendung|  
|--------------|---------|  
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Gibt eine kurze Beschreibung des Typs einer Laufzeitfehlerüberprüfung zurück.|  
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Gibt die Gesamtzahl der Fehler zurück, die durch die Laufzeitfehlerüberprüfungen erkannt werden können.|  
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Legt eine Funktion als Handler für das Melden von Laufzeitfehlerüberprüfungen fest.|  
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Ordnet einen Fehler, der von den Laufzeitfehlerüberprüfungen erkannt wurde, einem Typ zu.|  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)   
 [/RTC (Laufzeitfehlerüberprüfungen)](../build/reference/rtc-run-time-error-checks.md)   
 [runtime_checks](../preprocessor/runtime-checks.md)   
 [Debugroutinen](../c-runtime-library/debug-routines.md)
