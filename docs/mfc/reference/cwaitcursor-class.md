---
title: CWaitCursor-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
dev_langs:
- C++
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4867b98a9778c818ab19d5325782b24e29282fca
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077984"
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
|[CWaitCursor::CWaitCursor](#cwaitcursor)|Erstellt eine `CWaitCursor` -Objekts und zeigt den Wartecursor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CWaitCursor::Restore](#restore)|Stellt den Wartecursor wieder her, nachdem er geändert wurde, ist.|

## <a name="remarks"></a>Hinweise

`CWaitCursor` eine Basisklasse keinen.

Gute Methoden programming Windows erfordern, dass Sie einen Wartecursor angezeigt, wenn Sie einen Vorgang durchführen, der eine merklich Zeit akzeptiert.

Wenn einen Wartecursor anzeigen möchten, definieren Sie einfach eine `CWaitCursor` Variable vor dem Code, der den langwierigen Vorgang ausführt. Der Konstruktor des Objekts wird automatisch den Wartecursor angezeigt werden.

Wenn das Objekt den Gültigkeitsbereich verlässt (am Ende des Blocks in der die `CWaitCursor` -Objekt deklariert wird), dessen Destruktor legt den Cursor auf den vorherigen Cursor fest. Das heißt, führt das Objekt automatisch die erforderlichen Cleanup aus.

> [!NOTE]
>  Aufgrund ihrer Konstruktoren und Destruktoren wie arbeiten zu können `CWaitCursor` Objekte immer als lokale Variablen deklariert werden, sie noch nicht als globale Variablen deklariert werden, noch sind sie mit zugeordnet **neue**.

Wenn Sie einen Vorgang ausführen, die den Cursor geändert werden, z. B. das Anzeigen einer Meldung oder im Dialogfeld, rufen, verursachen, kann die [wiederherstellen](#restore) Memberfunktion versucht, den Wartecursor wiederherstellen. Es ist in Ordnung Aufrufen `Restore` selbst wenn ein Wartecursor derzeit angezeigt wird.

Eine andere Möglichkeit, einen Wartecursor angezeigt wird, verwenden Sie die Kombination von [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), und vielleicht [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). Allerdings `CWaitCursor` ist einfacher zu verwenden, da Sie keine müssen, setzen Sie den Cursor auf den vorherigen Cursor, wenn Sie mit der langwierige Vorgang ist fertig sind.

> [!NOTE]
>  MFC legt fest, und stellt die Cursor mit dem [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) virtuelle Funktion. Sie können diese Funktion, um benutzerdefiniertes Verhalten bereitstellen überschreiben.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CWaitCursor`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

## <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]

##  <a name="cwaitcursor"></a>  CWaitCursor::CWaitCursor

Deklarieren Sie zum Anzeigen eines eine `CWaitCursor` Objekt vor dem Code, der den langwierigen Vorgang ausführt.

```
CWaitCursor();
```

### <a name="remarks"></a>Hinweise

Der Konstruktor wird automatisch den Wartecursor angezeigt werden.

Wenn das Objekt den Gültigkeitsbereich verlässt (am Ende des Blocks in der die `CWaitCursor` -Objekt deklariert wird), dessen Destruktor legt den Cursor auf den vorherigen Cursor fest. Das heißt, führt das Objekt automatisch die erforderlichen Cleanup aus.

Sie können den Umstand nutzen, dass der Destruktor, am Ende des Blocks (die vor dem Ende der Funktion ggf.) aufgerufen wird um den Wartecursor in nur einen Teil Ihrer Funktion zu aktivieren. Diese Technik wird im zweiten Beispiel unten angezeigt.

> [!NOTE]
>  Aufgrund ihrer Konstruktoren und Destruktoren wie arbeiten zu können `CWaitCursor` Objekte immer als lokale Variablen deklariert werden, sie noch nicht als globale Variablen deklariert werden, noch sind sie mit zugeordnet **neue**.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]

##  <a name="restore"></a>  CWaitCursor::Restore

Wenn den Wartecursor wiederherstellen möchten, rufen Sie diese Funktion nach dem Ausführen eines Vorgangs, z. B. das Anzeigen von einem Meldungsfeld oder im Dialogfeld, das den Wartecursor an einen anderen Cursor ändern kann.

```
void Restore();
```

### <a name="remarks"></a>Hinweise

Es eignet sich zum Aufrufen `Restore` selbst wenn der Wartecursor derzeit angezeigt wird.

Wenn Sie den Wartecursor, während er sich in einer Funktion als die in der Wiederherstellung müssen die `CWaitCursor` Objekt deklariert ist, rufen Sie [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)<br/>
[CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)<br/>
[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)<br/>
[CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)<br/>
[I: wie den Mauszeiger auf eine Anwendung für Microsoft Foundation ändern](http://go.microsoft.com/fwlink/p/?linkid=128044)

