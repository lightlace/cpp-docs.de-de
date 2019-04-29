---
title: Initialisieren und Beenden der DAO-Datenbank-Engine
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.data
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 8ad0c1df2f5b6a7b1b48d2db119b04e4b3234f10
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323215"
---
# <a name="dao-database-engine-initialization-and-termination"></a>Initialisieren und Beenden der DAO-Datenbank-Engine

Verwendung von MFC-DAO-Objekten, muss zunächst die DAO-Datenbank-Engine werden initialisiert, und klicken Sie dann beendet, bevor Ihre Anwendung oder DLL beendet. Zwei Funktionen, `AfxDaoInit` und `AfxDaoTerm`, diese Aufgaben ausführen.

### <a name="dao-database-engine-initialization-and-termination"></a>Initialisieren und Beenden der DAO-Datenbank-Engine

|||
|-|-|
|[AfxDaoInit](#afxdaoinit)|Initialisiert die DAO-Datenbank-Engine.|
|[AfxDaoTerm](#afxdaoterm)|Beendet die DAO-Datenbank-Engine.|

##  <a name="afxdaoinit"></a>  AfxDaoInit

Diese Funktion initialisiert den DAO-Datenbankmoduls.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Hinweise

In den meisten Fällen müssen Sie nicht aufrufen `AfxDaoInit` da die Anwendung automatisch sie aufruft, wenn er benötigt wird.

Weitere Informationen und ein Beispiel eines Aufrufs `AfxDaoInit`, finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

##  <a name="afxdaoterm"></a>  AfxDaoTerm

Diese Funktion wird beendet, die DAO-Datenbank-Engine.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Hinweise

In der Regel müssen Sie nur zum Aufrufen dieser Funktion in einer regulären MFC-DLL. Ruft eine Anwendung automatisch `AfxDaoTerm` Wenn es erforderlich ist.

Rufen Sie in regulären MFC-DLLs `AfxDaoTerm` vor der `ExitInstance` -Funktion, allerdings erst, nachdem alle MFC-DAO-Objekte zerstört wurden.

Weitere Informationen finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
