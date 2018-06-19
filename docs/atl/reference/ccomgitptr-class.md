---
title: CComGITPtr Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
dev_langs:
- C++
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 049873ce6ff630e8f00ea5ad5ec9b3786bd5e71b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363625"
---
# <a name="ccomgitptr-class"></a>CComGITPtr-Klasse
Diese Klasse stellt Methoden für den Umgang mit Schnittstellenzeiger und der globalen Schnittstellentabelle (GIT).  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class CComGITPtr
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des den Schnittstellenzeiger in der GIT gespeichert werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComGITPtr::CComGITPtr](#ccomgitptr)|Der Konstruktor.|  
|[CComGITPtr:: ~ CComGITPtr](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComGITPtr::Attach](#attach)|Rufen Sie diese Methode, um den Schnittstellenzeiger in der globalen Schnittstellentabelle (GIT) zu registrieren.|  
|[CComGITPtr::CopyTo](#copyto)|Rufen Sie diese Methode, um die Schnittstelle aus der globalen Schnittstellentabelle (GIT) in den übergebenen Zeiger zu kopieren.|  
|[CComGITPtr::Detach](#detach)|Rufen Sie diese Methode, um die Zuordnung aufheben, die Schnittstelle aus der `CComGITPtr` Objekt.|  
|[CComGITPtr::GetCookie](#getcookie)|Rufen Sie diese Methode, um die Rückgabegröße des Cookies aus dem `CComGITPtr` Objekt.|  
|[CComGITPtr::Revoke](#revoke)|Rufen Sie diese Methode, um die Schnittstelle aus der globalen Schnittstellentabelle (GIT) zu entfernen.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComGITPtr::operator DWORD](#operator_dword)|Gibt das Cookie aus der `CComGITPtr` Objekt.|  
|[CComGITPtr::operator =](#operator_eq)|Zuweisungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComGITPtr::m_dwCookie](#m_dwcookie)|Das Cookie.|  
  
## <a name="remarks"></a>Hinweise  
 Objekte, die die freethreaded Marshaler aggregiert und Schnittstellenzeigern abgerufen, die von anderen Objekten verwenden müssen müssen zusätzliche Schritte Unternehmen, stellen Sie sicher, dass die Schnittstellen richtig gemarshallt werden. In der Regel umfasst dies den Schnittstellenzeiger in der GIT gespeichert und die Zeiger aus der GIT jedes Mal, die sie verwendet wird. Die Klasse `CComGITPtr` werden bereitgestellt, damit Sie in der GIT gespeicherten Schnittstellenzeigern verwenden.  
  
> [!NOTE]
>  Die globale Schnittstelle Tabelle-Funktion ist nur unter Windows 95 mit DCOM Version 1.1 und höher, Windows 98, Windows NT 4.0 mit Service Pack 3 oder höher und Windows 2000 verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="attach"></a>  CComGITPtr::Attach  
 Rufen Sie diese Methode, um den Schnittstellenzeiger in der globalen Schnittstellentabelle (GIT) zu registrieren.  
  
```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Der Schnittstellenzeiger des GIT hinzugefügt werden.  
  
 `dwCookie`  
 Das Cookie verwendet, um den Schnittstellenzeiger zu identifizieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds tritt ein Assertionsfehler, wenn die GIT ungültig ist oder wenn das Cookie gleich NULL ist.  
  
##  <a name="ccomgitptr"></a>  CComGITPtr::CComGITPtr  
 Der Konstruktor.  
  
```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `p`  
 Ein Schnittstellenzeiger in der globalen Schnittstellentabelle (GIT) gespeichert werden.  
  
 [in] `git`  
 Ein Verweis auf ein vorhandenes `CComGITPtr` Objekt.  
  
 [in] `dwCookie`  
 Ein Cookie verwendet, um den Schnittstellenzeiger zu identifizieren.  
  
 [in] `rv`  
 Die Quelle `CComGITPtr` Objekt, das Verschieben von Daten aus.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein neues `CComGITPtr` -Objekt, optional mit einem vorhandenen `CComGITPtr` Objekt.  
  
 Der Konstruktor Nutzung `rv` ein bewegungskonstruktor ist. Die Daten werden aus der Quelldatenbank übertragen `rv`, und klicken Sie dann `rv` deaktiviert ist.  
  
##  <a name="dtor"></a>  CComGITPtr:: ~ CComGITPtr  
 Der Destruktor.  
  
```
~CComGITPtr() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt die Schnittstelle aus der globalen Schnittstellentabelle (GIT), mit [CComGITPtr::Revoke](#revoke).  
  
##  <a name="copyto"></a>  CComGITPtr::CopyTo  
 Rufen Sie diese Methode, um die Schnittstelle aus der globalen Schnittstellentabelle (GIT) in den übergebenen Zeiger zu kopieren.  
  
```
HRESULT CopyTo(T** pp) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pp`  
 Der Zeiger die ist die Schnittstelle empfangen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittstelle aus dem GIT wird in den übergebenen Zeiger kopiert. Der Zeiger muss vom Aufrufer freigegeben werden, wenn es nicht mehr benötigt wird.  
  
##  <a name="detach"></a>  CComGITPtr::Detach  
 Rufen Sie diese Methode, um die Zuordnung aufheben, die Schnittstelle aus der `CComGITPtr` Objekt.  
  
```
DWORD Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Cookie aus der `CComGITPtr` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Es ist Aufgabe des Aufrufers So entfernen Sie die Schnittstelle aus dem GIT mit [CComGITPtr::Revoke](#revoke).  
  
##  <a name="getcookie"></a>  CComGITPtr::GetCookie  
 Rufen Sie diese Methode, um die Rückgabegröße des Cookies aus dem `CComGITPtr` Objekt.  
  
```
DWORD GetCookie() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Cookie zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Cookie ist eine Variable verwendet, um eine Schnittstelle und den Speicherort zu identifizieren.  
  
##  <a name="m_dwcookie"></a>  CComGITPtr::m_dwCookie  
 Das Cookie.  
  
```
DWORD m_dwCookie;
```  
  
### <a name="remarks"></a>Hinweise  
 Das Cookie wird eine Membervariable verwendet, um eine Schnittstelle und den Speicherort zu identifizieren.  
  
##  <a name="operator_eq"></a>  CComGITPtr::operator =  
 Der Zuweisungsoperator.  
  
```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `p`  
 Ein Zeiger auf eine Schnittstelle.  
  
 [in] `git`  
 Ein Verweis auf ein `CComGITPtr`-Objekt.  
  
 [in] `dwCookie`  
 Ein Cookie verwendet, um den Schnittstellenzeiger zu identifizieren.  
  
 [in] `rv`  
 Die `CComGITPtr` zum Verschieben von Daten aus.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CComGITPtr` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Weist einen neuen Wert zu einem `CComGITPtr` Objekt, das von einem vorhandenen Objekt oder einen Verweis auf eine globale Schnittstellentabelle.  
  
##  <a name="operator_dword"></a>  CComGITPtr::operator DWORD  
 Gibt das Cookie zugeordnet der `CComGITPtr` Objekt.  
  
```  
operator DWORD() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Das Cookie ist eine Variable verwendet, um eine Schnittstelle und den Speicherort zu identifizieren.  
  
##  <a name="revoke"></a>  CComGITPtr::Revoke  
 Rufen Sie diese Methode, um die aktuelle Schnittstelle aus der globalen Schnittstellentabelle (GIT) zu entfernen.  
  
```
HRESULT Revoke() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt die Schnittstelle aus dem GIT.  
  
## <a name="see-also"></a>Siehe auch  
 [Freethreaded Marshaler](../../atl/atl-and-the-free-threaded-marshaler.md)   
 [Zugreifen auf Schnittstellen über Apartments](http://msdn.microsoft.com/library/windows/desktop/ms682353)   
 [Verwenden der globalen Schnittstellentabelle](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
