---
title: CWaitCursor Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
dev_langs: C++
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1cf5c850158e445e7695b85e540b1e0c162e621c
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="cwaitcursor-class"></a>CWaitCursor-Klasse
Ermöglicht mit einer Befehlszeile die Anzeige eines Wartecursors (normalerweise in Form einer Sanduhr), während ein längeren Vorgang ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWaitCursor  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWaitCursor::CWaitCursor](#cwaitcursor)|Erstellt ein `CWaitCursor` -Objekt und zeigt den Wartecursor an.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWaitCursor::Restore](#restore)|Stellt den Wartecursor wieder her, nachdem er geändert wurde, ist.|  
  
## <a name="remarks"></a>Hinweise  
 `CWaitCursor`eine Basisklasse verfügt nicht über.  
  
 Gute Windows-Programmierung Methoden erfordern, dass einen Wartecursor angezeigt, wenn Sie einen Vorgang durchführen, der eine spürbar Zeit akzeptiert.  
  
 Um ein Wartecursor anzuzeigen, definieren Sie nur eine `CWaitCursor` Variable vor dem Code, der den langwierigen Vorgang ausführt. Der Konstruktor des Objekts wird automatisch den Wartecursor angezeigt werden.  
  
 Wenn das Objekt den Gültigkeitsbereich verlässt (am Ende des Blocks in der die `CWaitCursor` Objekt deklariert wird), dessen Destruktor setzt den Cursor auf den vorherigen Cursor. Das heißt, führt das Objekt automatisch den erforderlichen Cleanup aus.  
  
> [!NOTE]
>  Aufgrund ihrer Konstruktoren und Destruktoren Funktionsweise `CWaitCursor` Objekte immer als lokale Variablen deklariert werden – sie nie als globale Variablen deklariert sind, noch werden sie mit zugeordneten **neue**.  
  
 Wenn Sie einen Vorgang, der den Cursor ausführen geändert werden, z. B. das Anzeigen einer Meldungsfeld oder im Dialogfeld, rufen ggf. verursacht die [wiederherstellen](#restore) Memberfunktion den Wartecursor wiederherstellen. Es ist angemessen, rufen Sie **wiederherstellen** selbst wenn ein Wartecursor derzeit angezeigt wird.  
  
 Eine weitere Möglichkeit zum Anzeigen eines Wartecursor ist die Verwendung die Kombination von [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), und eventuell [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). Allerdings `CWaitCursor` ist einfacher zu verwenden, da Sie brauchen setzen Sie den Cursor auf den vorherigen Cursor, wenn Sie mit der längeren Vorgang fertig sind.  
  
> [!NOTE]
>  MFC legt fest, und den Cursor unter Verwendung der [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) virtuelle Funktion. Sie können diese Funktion, um benutzerdefiniertes Verhalten bereitzustellen, überschreiben.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CWaitCursor`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]  
  
##  <a name="cwaitcursor"></a>CWaitCursor::CWaitCursor  
 Deklarieren Sie zum Anzeigen eines Wartecursor ein `CWaitCursor` Objekt vor dem Code, der den langwierigen Vorgang ausführt.  
  
```  
CWaitCursor();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor wird automatisch den Wartecursor angezeigt werden.  
  
 Wenn das Objekt den Gültigkeitsbereich verlässt (am Ende des Blocks in der die `CWaitCursor` Objekt deklariert wird), dessen Destruktor setzt den Cursor auf den vorherigen Cursor. Das heißt, führt das Objekt automatisch den erforderlichen Cleanup aus.  
  
 Sie können den Umstand nutzen, dass der Destruktor, am Ende des Blocks (die vor dem Ende der Funktion möglicherweise) aufgerufen wird um den Wartecursor in nur einen Teil Ihrer Funktion zu aktivieren. Diese Technik wird im zweiten Beispiel unten angezeigt.  
  
> [!NOTE]
>  Aufgrund ihrer Konstruktoren und Destruktoren Funktionsweise `CWaitCursor` Objekte immer als lokale Variablen deklariert werden – sie nie als globale Variablen deklariert sind, noch werden sie mit zugeordneten **neue**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]  
  
##  <a name="restore"></a>CWaitCursor::Restore  
 Wenn den Wartecursor wiederherstellen möchten, rufen Sie diese Funktion nach dem Ausführen eines Vorgangs, z. B. das Anzeigen einer Meldungsfeld oder (Dialogfeld), das den Wartecursor in einen anderen Cursor geändert werden kann.  
  
```  
void Restore();
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist in Ordnung Aufrufen **wiederherstellen** selbst wenn der Wartecursor derzeit angezeigt wird.  
  
 Wenn Sie in der eine Funktion als die in dem den Wartecursor wiederherstellen müssen die `CWaitCursor` Objekt deklariert ist, rufen Sie [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)   
 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)   
 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)   
 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)   
 [Wie ändere I: den Mauszeiger auf eine Anwendung für Microsoft Foundation](http://go.microsoft.com/fwlink/p/?linkid=128044)



