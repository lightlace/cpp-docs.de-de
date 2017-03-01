---
title: Klasse CUserException | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserException
dev_langs:
- C++
helpviewer_keywords:
- operations [C++], stopping
- exceptions, throwing
- CUserException class
- errors [C++], trapping
- operations [C++]
- throwing exceptions, stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 23
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8548ffa7ad9032e174d650e210a70a29b0e3f19d
ms.lasthandoff: 02/24/2017

---
# <a name="cuserexception-class"></a>CUserException-Klasse
Wird ausgelöst, um einen Endbenutzervorgang zu beenden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie `CUserException` Wenn Ausnahmemechanismus Throw/Catch für anwendungsspezifische Ausnahmen verwendet werden sollen. "User" in der Klassenname kann interpretiert werden, wie"Meine Benutzer etwas außergewöhnlichen, behandelt werden muss."  
  
 Ein `CUserException` ausgelöst, in der Regel nach dem Aufrufen der globalen Funktion `AfxMessageBox` zur Benachrichtigung des Benutzers, der ein Vorgang fehlgeschlagen ist. Wenn Sie einen Ausnahmehandler schreiben, behandeln Sie die Ausnahme, besonders, da der Benutzer bereits in der Regel Fehler benachrichtigt wurde. Das Framework löst diese Ausnahme in einigen Fällen. Auslösen einer `CUserException` selbst den Benutzer zu warnen, und rufen Sie anschließend die globale Funktion `AfxThrowUserException`.  
  
 Im folgenden Beispiel eine Funktion, die Vorgänge, die möglicherweise fehlschlagen, benachrichtigt den Benutzer, und löst eine `CUserException`. Die aufrufende Funktion fängt die Ausnahme ab und verarbeitet sie speziell:  
  
 [!code-cpp[NVC_MFCExceptions&#24;](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 Weitere Informationen zur Verwendung von `CUserException`, finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)

