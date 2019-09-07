---
title: _U_STRINGorID-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
ms.openlocfilehash: c57d983e9680ce6d2cab375e427b80f4d3b6c2d6
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739582"
---
# <a name="_u_stringorid-class"></a>_U_STRINGorID-Klasse

Diese Argument Adapter Klasse ermöglicht das Übergeben von Ressourcennamen (lpctstrans) oder Ressourcen-IDs (uint) an eine Funktion, ohne dass der Aufrufer die ID mithilfe des makeintresource-Makros in eine Zeichenfolge konvertieren muss.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class _U_STRINGorID
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|Der Konstruktor.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|Der Ressourcen Bezeichner.|

## <a name="remarks"></a>Hinweise

Diese Klasse ist für die Implementierung von Wrappern für die Windows-Ressourcenverwaltungs-API konzipiert, wie z. b. die Funktionen [FindResource](/windows/win32/api/winbase/nf-winbase-findresourcea), [LoadIcon](/windows/win32/api/winuser/nf-winuser-loadiconw)und [loadmenu](/windows/win32/api/winuser/nf-winuser-loadmenuw) , die ein LPCTSTR-Argument akzeptieren, das entweder den Namen einer Ressource oder die zugehörige ID aufweisen kann.

Die-Klasse definiert zwei Konstruktorüberladungen: eine akzeptiert ein LPCTSTR-Argument, und die andere akzeptiert ein uint-Argument. Das uint-Argument wird in einen Ressourcentyp konvertiert, der mit den Windows-Ressourcen Verwaltungsfunktionen kompatibel ist. dabei wird das makeintresource-Makro verwendet, und das Ergebnis wird im einzelnen Datenmember der Klasse [m_lpstr](#_u_stringorid__m_lpstr)gespeichert. Das Argument für den LPCTSTR-Konstruktor wird ohne Konvertierung direkt gespeichert.

## <a name="requirements"></a>Anforderungen

**Header:** atlwin. h

##  <a name="_u_stringorid__m_lpstr"></a>_U_STRINGorID::m_lpstr

Die-Klasse enthält den Wert, der an einen ihrer Konstruktoren als öffentliches LPCTSTR-Datenmember übergeben wird.

```
LPCTSTR m_lpstr;
```

##  <a name="_u_stringorid___u_stringorid"></a>_U_STRINGorID::_U_STRINGorID

Der uint-Konstruktor konvertiert sein Argument in einen Ressourcentyp, der mit Windows-Ressourcen Verwaltungsfunktionen kompatibel ist, indem das makeintresource-Makro verwendet wird, und das Ergebnis wird im einzelnen Datenmember der Klasse, [m_lpstr](#_u_stringorid__m_lpstr), gespeichert.

```
_U_STRINGorID(UINT nID);
_U_STRINGorID(LPCTSTR lpString);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Eine Ressourcen-ID.

*lpString*<br/>
Ein Ressourcen Name.

### <a name="remarks"></a>Hinweise

Das Argument für den LPCTSTR-Konstruktor wird ohne Konvertierung direkt gespeichert.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
