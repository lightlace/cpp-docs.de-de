---
title: CSimpleException-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ab21338eabe2e432189ccf8a5aae3432005657d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083216"
---
# <a name="csimpleexception-class"></a>CSimpleException-Klasse

Diese Klasse ist eine Basisklasse für ressourcenkritische MFC-Ausnahmen.

## <a name="syntax"></a>Syntax

```
class AFX_NOVTABLE CSimpleException : public CException
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSimpleException::CSimpleException](#csimpleexception)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSimpleException::GetErrorMessage](#geterrormessage)|Stellt Text zu einem Fehler, der aufgetreten ist.|

## <a name="remarks"></a>Hinweise

`CSimpleException` ist die Basisklasse für kritische Ressourcen MFC-Ausnahmen und behandelt, die Besitz und die Initialisierung einer Fehlermeldung. Folgende Klassen geben mit `CSimpleException` als Basisklasse:

|||
|-|-|
|[CMemoryException-Klasse](../../mfc/reference/cmemoryexception-class.md)|Out-of-Memory-Ausnahme|
|[CNotSupportedException-Klasse](../../mfc/reference/cnotsupportedexception-class.md)|Anforderungen für einen nicht unterstützten Vorgang|
|[CResourceException-Klasse](../../mfc/reference/cresourceexception-class.md)|Windows-Ressource wurde nicht gefunden oder keine erstellbaren Objekts.|
|[CUserException-Klasse](../../mfc/reference/cuserexception-class.md)|Ausnahme, eine Ressource angibt, wurde nicht gefunden|
|[CInvalidArgException-Klasse](../../mfc/reference/cinvalidargexception-class.md)|Ausnahme, die ein ungültiges Argument angibt.|

Da `CSimpleException` ist eine abstrakte Basisklasse, kann nicht deklariert eine `CSimpleException` direkt. Stattdessen müssen Sie die abgeleitete Objekte, z. B. in der vorherigen Tabelle deklarieren. Wenn Sie Ihre eigene abgeleitete Klasse deklarieren, verwenden Sie die vorherigen Klassen als Modell aus.

Weitere Informationen finden Sie unter den [CException-Klasse](../../mfc/reference/cexception-class.md) Thema und [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="csimpleexception"></a>  CSimpleException::CSimpleException

Der Konstruktor.

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Parameter

*bAutoDelete*<br/>
Geben Sie "true", wenn der Speicher für die `CSimpleException` Objekt auf dem Heap zugewiesen wurde. Dies bewirkt, dass die `CSimpleException` zu beim löschendes Objekt die `Delete` Member-Funktion wird aufgerufen, um die Ausnahme zu löschen. Geben Sie "false", wenn die `CSimpleException` Objekt ist auf dem Stapel oder ein globales Objekt. In diesem Fall die `CSimpleException` Objekt werden nicht gelöscht, wenn die `Delete` Memberfunktion aufgerufen wird.

### <a name="remarks"></a>Hinweise

Sie müssen normalerweise nicht direkt aufrufen dieses Konstruktors. Eine Funktion, die eine Ausnahme auslöst, sollte eine Instanz der Erstellen einer `CException`-abgeleitete Klasse und rufen Sie ihren Konstruktor, oder es sollte gehen wie die MFC-Bibliothek auslösen, Funktionen, z. B. [AfxThrowFileException](exception-processing.md#afxthrowfileexception), um einen vordefinierten Typ auslösen.

##  <a name="geterrormessage"></a>  CSimpleException::GetErrorMessage

Rufen Sie diese Memberfunktion, um Text zu einem Fehler bereitzustellen, die aufgetreten ist.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>Parameter

*lpszError*<br/>
Ein Zeiger auf einen Puffer, der eine Fehlermeldung angezeigt wird.

*nMaxError*<br/>
Die maximale Anzahl von Zeichen, die der Puffer aufnehmen kann, einschließlich des NULL-Abschlusszeichens.

*pnHelpContext*<br/>
Die Adresse einer "uint", die die Hilfekontext-ID. erhalten Wenn der Wert NULL ist, wird keine ID zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; Andernfalls ist 0, wenn kein Text der Fehlermeldung zur Verfügung.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CException-Klasse](../../mfc/reference/cexception-class.md)<br/>
[Ausnahmebehandlung](../../mfc/exception-handling-in-mfc.md)

