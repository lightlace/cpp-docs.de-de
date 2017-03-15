---
title: Klasse CWaitCursor | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWaitCursor
dev_langs:
- C++
helpviewer_keywords:
- cursors, wait cursor
- CWaitCursor class
- wait cursors
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f72598c356add5d891b013f1fd7b87665c5a6c63
ms.lasthandoff: 02/24/2017

---
# <a name="cwaitcursor-class"></a>CWaitCursor-Klasse
Ermöglicht mit einer Befehlszeile die Anzeige eines Wartecursors (normalerweise in Form einer Sanduhr), während ein längeren Vorgang ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWaitCursor  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWaitCursor::CWaitCursor](#cwaitcursor)|Erstellt ein `CWaitCursor` -Objekt und zeigt den Wartecursor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWaitCursor::Restore](#restore)|Den Wartecursor wiederhergestellt, nachdem sie geändert wurde.|  
  
## <a name="remarks"></a>Hinweise  
 `CWaitCursor`eine Basisklasse keinen.  
  
 Gute Programmiertechniken Windows müssen Sie einen Wartecursor angezeigt, wenn Sie einen Vorgang ausführen, der eine merkliche viel Zeit beansprucht.  
  
 Zum einen Wartecursor anzeigen zu können, definieren Sie nur eine `CWaitCursor` Variablen vor dem Code, der den langwierigen Vorgang ausführt. Der Konstruktor des Objekts wird automatisch den Wartecursor angezeigt werden.  
  
 Wenn das Objekt den Gültigkeitsbereich verlässt (am Ende des Blocks, in dem die `CWaitCursor` Objekt deklariert wird), dessen Destruktor setzt den Cursor auf den vorherigen Cursor. Das heißt, das Objekt erforderlichen bereinigt automatisch ausgeführt.  
  
> [!NOTE]
>  Aufgrund ihrer Konstruktoren und Destruktoren Funktionsweise `CWaitCursor` Objekte werden immer als lokale Variablen deklariert – sie nie als globale Variablen deklariert sind, noch werden diese mit zugeordnet **neue**.  
  
 Wenn Sie einen Vorgang, die den Cursor ausführen geändert werden, z. B. das Anzeigen einer Meldung oder im Dialogfeld, rufen möglicherweise die [wiederherstellen](#restore) -Memberfunktion den Wartecursor wiederherstellen. Es ist in Ordnung, rufen Sie **wiederherstellen** selbst wenn ein Wartecursor derzeit angezeigt wird.  
  
 Eine weitere Möglichkeit zum Anzeigen eines ist die Verwendung der Kombination von [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), und vielleicht [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). Allerdings `CWaitCursor` ist einfacher zu verwenden, weil Sie nicht benötigen, setzen Sie den Cursor auf den vorherigen Cursor, wenn Sie mit der langwierige Vorgang fertig sind.  
  
> [!NOTE]
>  MFC legt fest, und stellt den Cursor mithilfe der [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) virtuellen Funktion. Überschreiben Sie diese Funktion, um benutzerdefiniertes Verhalten bereitzustellen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CWaitCursor`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#62;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]  
  
##  <a name="a-namecwaitcursora--cwaitcursorcwaitcursor"></a><a name="cwaitcursor"></a>CWaitCursor::CWaitCursor  
 Deklarieren Sie zum Anzeigen eines Wartecursor ein `CWaitCursor` Objekt vor dem Code, der den langwierigen Vorgang ausführt.  
  
```  
CWaitCursor();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor wird automatisch den Wartecursor angezeigt werden.  
  
 Wenn das Objekt den Gültigkeitsbereich verlässt (am Ende des Blocks, in dem die `CWaitCursor` Objekt deklariert wird), dessen Destruktor setzt den Cursor auf den vorherigen Cursor. Das heißt, das Objekt erforderlichen bereinigt automatisch ausgeführt.  
  
 Sie können die Tatsache nutzen, dass der Destruktor, am Ende des Blocks (die vor dem Ende der Funktion sein kann) aufgerufen wird um den Wartecursor in nur einen Teil Ihrer Funktion zu aktivieren. Diese Technik wird im zweiten Beispiel unten angezeigt.  
  
> [!NOTE]
>  Aufgrund ihrer Konstruktoren und Destruktoren Funktionsweise `CWaitCursor` Objekte werden immer als lokale Variablen deklariert – sie nie als globale Variablen deklariert sind, noch werden diese mit zugeordnet **neue**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#63;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]  
  
##  <a name="a-namerestorea--cwaitcursorrestore"></a><a name="restore"></a>CWaitCursor::Restore  
 Wenn den Wartecursor wiederherstellen möchten, rufen Sie diese Funktion nach dem Ausführen eines Vorgangs, z. B. das Anzeigen von einem Meldungsfeld oder ein Dialogfeld, das den Wartecursor zu einem anderen Cursor ändern kann.  
  
```  
void Restore();
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist in Ordnung, rufen Sie **wiederherstellen** selbst wenn der Wartecursor derzeit angezeigt wird.  
  
 Wenn Sie in eine andere Funktion als eine, in der den Wartecursor wiederherstellen müssen die `CWaitCursor` Objekt deklariert ist, rufen Sie [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#64;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)   
 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)   
 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)   
 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)   
 [I: wie den Cursor in eine Anwendung für Microsoft Foundation ändern](http://go.microsoft.com/fwlink/linkid=128044)




