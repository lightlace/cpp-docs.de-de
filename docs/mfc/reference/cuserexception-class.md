---
title: CUserException-Klasse
ms.date: 11/04/2016
f1_keywords:
- CUserException
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
ms.openlocfilehash: 72d8537616792859a2b00a1a5cd880ce5eb452bf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304586"
---
# <a name="cuserexception-class"></a>CUserException-Klasse

Wird ausgelöst, um einen Endbenutzervorgang zu beenden.

## <a name="syntax"></a>Syntax

```
class CUserException : public CSimpleException
```

## <a name="remarks"></a>Hinweise

Verwenden Sie `CUserException` Wenn Sie den Throw/Catch-Ausnahmemechanismus für Ausnahmen, die anwendungsspezifische verwenden möchten. "User" in den Namen der Klasse kann interpretiert werden, wie"Meine Benutzer etwas außergewöhnliche, behandelt werden muss."

Ein `CUserException` wird in der Regel ausgelöst werden, nach dem Aufrufen der globalen Funktion `AfxMessageBox` zur Benachrichtigung des Benutzers, der ein Vorgang fehlgeschlagen ist. Wenn Sie einen Ausnahmehandler schreiben, behandeln Sie die Ausnahme, besonders, da der Benutzer bereits in der Regel für den Fehler benachrichtigt wurde. Das Framework löst diese Ausnahme in einigen Fällen. Auslösen einer `CUserException` selbst den Benutzer zu warnen, und rufen Sie dann auf die globale Funktion `AfxThrowUserException`.

Im folgenden Beispiel wird eine Funktion, die Vorgänge, die ggf. zu einem Fehler enthält, benachrichtigt den Benutzer, und löst eine `CUserException`. Die aufrufende Funktion fängt die Ausnahme ab und speziell behandelt:

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

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CException-Klasse](../../mfc/reference/cexception-class.md)
