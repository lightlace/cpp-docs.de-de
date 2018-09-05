---
title: _U_RECT-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
dev_langs:
- C++
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1041141e9f31e59ab7a1884e976828972c0abd91
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767323"
---
# <a name="urect-class"></a>_U_RECT-Klasse

Dieses Argument-Adapterklasse ermöglicht `RECT` Zeigern oder verweisen auf eine Funktion übergeben werden, die im Hinblick auf Zeigern implementiert wird.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class _U_RECT
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[_U_RECT::_U_RECT](#_u_rect___u_rect)|Der Konstruktor.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[_U_RECT::m_lpRect](#_u_rect__m_lprect)|Zeiger auf eine `RECT`.|

## <a name="remarks"></a>Hinweise

Die Klasse definiert zwei Konstruktorüberladungen: eine akzeptiert eine **RECT &** Argument und der andere akzeptiert einen `LPRECT` Argument. Der erste Konstruktor speichert die Adresse des Arguments Verweis in der Klasse der einzelnen Datenmember, [M_lpRect](#_u_rect__m_lprect). Das Argument an den Konstruktor der Zeiger wird direkt ohne Konvertierung gespeichert.

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="_u_rect__m_lprect"></a>  _U_RECT::m_lpRect

Die Klasse enthält den Wert, der auf seine Konstruktoren übergeben wird, als öffentliche `LPRECT` -Datenmember.

```
LPRECT m_lpRect;
```

##  <a name="_u_rect___u_rect"></a>  _U_RECT::_U_RECT

Die Adresse des Arguments Verweis wird gespeichert, in der Klasse der einzelnen Datenmember, [M_lpRect](#_u_rect__m_lprect).

```
_U_RECT(RECT& rc);  
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>Parameter

*RC*  
Ein `RECT` Verweis.

*lpRect*  
Ein `RECT` Zeiger.

### <a name="remarks"></a>Hinweise

Das Argument an den Konstruktor der Zeiger wird direkt ohne Konvertierung gespeichert.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
