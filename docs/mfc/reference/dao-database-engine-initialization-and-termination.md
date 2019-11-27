---
title: Initialisieren und Beenden der DAO-Datenbank-Engine
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 24a24d5a81da18d01472fc760c2adf96ee9868d5
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303462"
---
# <a name="dao-database-engine-initialization-and-termination"></a>Initialisieren und Beenden der DAO-Datenbank-Engine

DAO wird für Access-Datenbanken verwendet und wird von Office 2013 unterstützt. DAO 3,6 ist die endgültige Version, die als veraltet eingestuft wird. Bei der Verwendung von MFC-DAO-Objekten muss das DAO-Datenbankmodul zunächst initialisiert und dann beendet werden, bevor die Anwendung oder dll abgebrochen wird. Diese Aufgaben werden von zwei Funktionen, `AfxDaoInit` und `AfxDaoTerm`, ausgeführt.

### <a name="dao-database-engine-initialization-and-termination"></a>Initialisieren und Beenden der DAO-Datenbank-Engine

|||
|-|-|
|[Afxdaoinit](#afxdaoinit)|Initialisiert die DAO-Datenbank-Engine.|
|[AfxDaoTerm](#afxdaoterm)|Beendet das DAO-Datenbankmodul.|

##  <a name="afxdaoinit"></a>Afxdaoinit

Mit dieser Funktion wird die DAO-Datenbank-Engine initialisiert.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Hinweise

In den meisten Fällen müssen Sie `AfxDaoInit` nicht aufrufen, da die Anwendung Sie automatisch aufruft, wenn Sie benötigt wird.

Weitere Informationen und ein Beispiel für das Aufrufen von `AfxDaoInit`finden Sie im [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Voraussetzungen

  **Header** afxdao. h

##  <a name="afxdaoterm"></a>AfxDaoTerm

Diese Funktion beendet das DAO-Datenbankmodul.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Hinweise

In der Regel müssen Sie diese Funktion nur in einer regulären MFC-DLL abrufen. eine Anwendung ruft `AfxDaoTerm` automatisch auf, wenn Sie benötigt wird.

In regulären MFC-DLLs wird `AfxDaoTerm` vor der `ExitInstance` Funktion aufgerufen, aber nachdem alle MFC-DAO-Objekte zerstört wurden.

Weitere Informationen finden Sie im [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Voraussetzungen

  **Header** afxdao. h

## <a name="see-also"></a>Siehe auch

[Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md)
