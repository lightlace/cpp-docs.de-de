---
title: "Durch das Auslösen von Softwareausnahmen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- run-time errors, treating as exceptions
- exception handling [C++], errors as exceptions
- exceptions [C++], flagging errors as exceptions
- errors [C++], treating as exceptions
- exception handling [C++], detecting errors
- structured exception handling [C++], errors as exceptions
- exceptions [C++], software
- RaiseException function
- software exceptions [C++]
- formats [C++], exception codes
ms.assetid: be1376c3-c46a-4f52-ad1d-c2362840746a
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 333db5bf60d8b542a69efb3dba9d39c624e8b605
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="raising-software-exceptions"></a>Auslösen von Softwareausnahmen
Einige der häufigsten Programmfehlerquellen werden vom System nicht als Ausnahmen gekennzeichnet. Wenn Sie beispielsweise versuchen, einen Speicherblock zu belegen, jedoch unzureichend Arbeitsspeicher vorhanden ist, löst die Laufzeit oder API-Funktion keine Ausnahme aus, sondern gibt einen Fehlercode zurück.  
  
 Sie können jedoch jede Bedingung als Ausnahme behandeln, durch das erkennen diese Bedingung in Ihrem Code, und melden es dann durch Aufrufen der [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552) Funktion. Indem Sie Fehler auf diese Weise kennzeichnen, können Sie die Vorteile der strukturierten Ausnahmebehandlung für jede Art von Laufzeitfehler nutzen.  
  
 So verwenden Sie die strukturierte Ausnahmebehandlung bei Fehlern  
  
-   Definieren Sie einen eigenen Ausnahmecode für das Ereignis.  
  
-   Rufen Sie **RaiseException** Wenn Sie ein Problem feststellen.  
  
-   Verwenden Sie Ausnahmebehandlungsfilter, um den von Ihnen definierten Ausnahmecode zu testen.  
  
 Die Datei "WINERROR.H" enthält das Format für Ausnahmecodes. Um sicherzustellen, dass Sie keinen Code definieren, der in Konflikt mit einem vorhandenen Ausnahmecode steht, legen Sie das dritte höchstwertige Bit auf 1 fest. Die vier höchstwertigen Bits sollten so festgelegt werden, wie in der folgenden Tabelle gezeigt.  
  
|Bits|Empfohlene Binäreinstellung|Beschreibung|  
|----------|--------------------------------|-----------------|  
|31-30|11|Diese zwei Bits beschreiben den grundlegenden Status des Codes: 11 = Fehler, 00 = Erfolg, 01 = Information, 10 = Warnung.|  
|29|1|Clientbit. Wird für benutzerdefinierten Code auf 1 festgelegt.|  
|28|0|Reservierte Bitzahl. (Festlegung auf 0 beibehalten.)|  
  
 Sie können die ersten zwei Bits optional auf eine andere Einstellung als binär 11 festlegen, obwohl die Einstellung "Fehler" für die meisten Ausnahmen angemessen ist. Es ist wichtig, daran zu denken, Bits 29 und 28 so festzulegen, wie es in der vorherigen Tabelle gezeigt wurde.  
  
 Das fehlercodeergebnis sollte daher die vier höchsten Bits auf hexadezimales e festgelegt haben. Die folgenden Definitionen definieren beispielsweise Ausnahmecodes, die keinen Konflikt mit jeder Windows-Ausnahmecodes. (Sie müssen jedoch prüfen, welche Codes von Drittanbieter-DLLs verwendet werden).  
  
```  
#define STATUS_INSUFFICIENT_MEM       0xE0000001  
#define STATUS_FILE_BAD_FORMAT        0xE0000002  
```  
  
 Nachdem Sie einen Ausnahmecode definiert haben, können Sie ihn verwenden, um eine Ausnahme auszulösen. Zum Beispiel löst der folgende Code die STATUS_INSUFFICIENT_MEM-Ausnahme als Reaktion auf ein Problem mit der Speicherbelegung aus:  
  
```  
lpstr = _malloc( nBufferSize );  
if (lpstr == NULL)  
    RaiseException( STATUS_INSUFFICIENT_MEM, 0, 0, 0);  
```  
  
 Wenn Sie einfach eine Ausnahme auslösen möchten, können Sie die letzten drei Parameter auf 0 festlegen. Die drei letzten Parameter übergeben zusätzliche Informationen und legen Flags fest, die Handler beim Fortsetzen der Ausführung hindern. Finden Sie unter der [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552) -Funktion in der [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] für Weitere Informationen.  
  
 In den Ausnahmebehandlungsfiltern können Sie dann die Codes testen, die Sie definiert haben. Zum Beispiel:  
  
```  
__try {  
    ...  
}  
__except (GetExceptionCode() == STATUS_INSUFFICIENT_MEM ||  
        GetExceptionCode() == STATUS_FILE_BAD_FORMAT )  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
