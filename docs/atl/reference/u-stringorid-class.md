---
title: _U_STRINGorID Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: b02d539ae2a067c015988a847407bf631b6e8c1a
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="ustringorid-class"></a>_U_STRINGorID-Klasse
Dieses Argument-Adapterklasse ermöglicht entweder Ressourcennamen ( `LPCTSTR`s) oder Ressourcen-IDs ( **"uint"**s) an eine Funktion übergeben werden, ohne dass des Aufrufers in eine Zeichenfolge mit der ID konvertieren die **MAKEINTRESOURCE** Makro.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class _U_STRINGorID
```  
  
## <a name="members"></a>Mitglieder  
  
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
  
##  <a name="_u_stringorid__m_lpstr"></a>_U_STRINGorID::m_lpstr  
 Die Klasse enthält den Wert, der entweder seiner Konstruktoren übergeben, als öffentliche `LPCTSTR` -Datenmember.  
  
```
LPCTSTR m_lpstr;
```  
  
##  <a name="_u_stringorid___u_stringorid"></a>_U_STRINGorID::_U_STRINGorID  
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

