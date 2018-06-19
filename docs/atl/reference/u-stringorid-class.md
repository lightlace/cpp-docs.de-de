---
title: _U_STRINGorID Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
dev_langs:
- C++
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a601b1c64b28681c13a0b9e8f42156d8820cb4b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359661"
---
# <a name="ustringorid-class"></a>_U_STRINGorID-Klasse
Dieses Argument-Adapterklasse ermöglicht entweder Ressourcennamen ( `LPCTSTR`s) oder Ressourcen-IDs ( **"uint"** s) an eine Funktion übergeben werden, ohne dass des Aufrufers in eine Zeichenfolge mit der ID konvertieren die **MAKEINTRESOURCE** Makro.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
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
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|Der Ressourcenbezeichner.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse dient zur Implementierung der Windows-Ressource-Verwaltungs-API-Wrapper, z. B. die [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042), [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), und [LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990) -Funktionen, die akzeptieren ein `LPCTSTR` Argument, das möglicherweise entweder den Namen einer Ressource oder ihre-ID  
  
 Die Klasse definiert zwei Konstruktorüberladungen: einer akzeptiert eine `LPCTSTR` Argument und die andere akzeptiert einen **"uint"** Argument. Die **"uint"** Argument in einen Ressourcentyp kompatibel mit Windows-Ressource-Management-Funktionen mit konvertiert die **MAKEINTRESOURCE** -Makro und das Ergebnis in die Klasse der einzelnen Datenmember, gespeicherten [M_lpstr](#_u_stringorid__m_lpstr). Das Argument für die `LPCTSTR` Konstruktor direkt ohne Konvertierung gespeichert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="_u_stringorid__m_lpstr"></a>  _U_STRINGorID::m_lpstr  
 Die Klasse enthält den Wert, der entweder seiner Konstruktoren übergeben, als öffentliche `LPCTSTR` -Datenmember.  
  
```
LPCTSTR m_lpstr;
```  
  
##  <a name="_u_stringorid___u_stringorid"></a>  _U_STRINGorID::_U_STRINGorID  
 Die **"uint"** Konstruktor konvertiert das Argument in einen Ressourcentyp kompatibel mit Windows-Ressource-Management-Funktionen mithilfe der **MAKEINTRESOURCE** -Makro und das Ergebnis wird in der Klasse einzelnen gespeichert Datenmember, [M_lpstr](#_u_stringorid__m_lpstr).  
  
```
_U_STRINGorID(UINT nID);  
_U_STRINGorID(LPCTSTR lpString);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Ein Ressourcen-ID.  
  
 `lpString`  
 Der Name einer Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Das Argument für die `LPCTSTR` Konstruktor direkt ohne Konvertierung gespeichert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
