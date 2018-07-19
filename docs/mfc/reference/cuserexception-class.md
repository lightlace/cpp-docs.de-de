---
title: CUserException Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CUserException
dev_langs:
- C++
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1701f6894ba3b44205526c59bad7ef635c1bbbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369472"
---
# <a name="cuserexception-class"></a>CUserException-Klasse
Wird ausgelöst, um einen Endbenutzervorgang zu beenden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie `CUserException` Wenn Throw/Catch-Ausnahmemechanismus für anwendungsspezifische Ausnahmen verwendet werden sollen. "User" in der Klassenname kann interpretiert werden, wie"Meine Benutzer etwas herausragende, dass ich behandeln müssen."  
  
 Ein `CUserException` wird in der Regel nach dem Aufrufen der globalen Funktion ausgelöst `AfxMessageBox` um Benutzer zu benachrichtigen, die ein Vorgang fehlgeschlagen ist. Wenn Sie einen Ausnahmehandler schreiben, behandeln Sie die Ausnahme, speziell, da der Benutzer bereits in der Regel den Fehler benachrichtigt wurde. Das Framework löst diese Ausnahme in einigen Fällen. Auslösen einer `CUserException` selbst, der Benutzer gewarnt werden, und rufen Sie dann auf die globale Funktion `AfxThrowUserException`.  
  
 Im folgenden Beispiel wird eine Funktion, die mit Vorgängen, die fehlschlagen, warnt den Benutzer, und löst eine `CUserException`. Die aufrufende Funktion fängt die Ausnahme ab und verarbeitet sie speziell:  
  
 [!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 Weitere Informationen zur Verwendung von `CUserException`, finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)
