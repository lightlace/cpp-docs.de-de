---
title: Initialisieren und Beenden der DAO-Datenbank-Engine
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: ccdf2e7b0f31576dddccad016e6b32806cdb82bf
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095884"
---
# <a name="dao-database-engine-initialization-and-termination"></a>Initialisieren und Beenden der DAO-Datenbank-Engine

DAO wird für Access-Datenbanken verwendet und wird von Office 2013 unterstützt. 3,6 ist die endgültige Version und wird als veraltet eingestuft. Bei der Verwendung von MFC-DAO-Objekten muss das DAO-Datenbankmodul zunächst initialisiert und dann beendet werden, bevor die Anwendung oder dll abgebrochen wird. Zwei Funktionen, `AfxDaoInit` und `AfxDaoTerm`, führen diese Aufgaben aus.

### <a name="dao-database-engine-initialization-and-termination"></a>Initialisieren und Beenden der DAO-Datenbank-Engine

|||
|-|-|
|[AfxDaoInit](#afxdaoinit)|Initialisiert die DAO-Datenbank-Engine.|
|[AfxDaoTerm](#afxdaoterm)|Beendet das DAO-Datenbankmodul.|

##  <a name="afxdaoinit"></a>Afxdaoinit

Mit dieser Funktion wird die DAO-Datenbank-Engine initialisiert.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Hinweise

In den meisten Fällen müssen Sie nicht aufrufen `AfxDaoInit` , da die Anwendung Sie automatisch aufruft, wenn Sie benötigt wird.

Weitere Informationen und ein Beispiel für den Aufruf `AfxDaoInit`von finden Sie im [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdao. h

##  <a name="afxdaoterm"></a>AfxDaoTerm

Diese Funktion beendet das DAO-Datenbankmodul.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Hinweise

In der Regel müssen Sie diese Funktion nur in einer regulären MFC-DLL abrufen. eine Anwendung wird automatisch aufgerufen `AfxDaoTerm` , wenn Sie benötigt wird.

In regulären MFC-DLLs wird `AfxDaoTerm` vor der `ExitInstance` -Funktion aufgerufen, aber nachdem alle MFC-DAO-Objekte zerstört wurden.

Weitere Informationen finden Sie im [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdao. h

## <a name="see-also"></a>Siehe auch

[Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md)
