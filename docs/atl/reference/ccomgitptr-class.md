---
title: Klasse CComGITPtr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9fe9d9f6d03a6d72c1ce3332419c738570a53803
ms.lasthandoff: 02/24/2017

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
 Der Typ den Schnittstellenzeiger in der GIT gespeichert werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComGITPtr::CComGITPtr](#ccomgitptr)|Der Konstruktor.|  
|[CComGITPtr:: ~ CComGITPtr](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComGITPtr::Attach](#attach)|Rufen Sie diese Methode, um den Schnittstellenzeiger in der globalen Schnittstellentabelle (GIT) zu registrieren.|  
|[CComGITPtr::CopyTo](#copyto)|Rufen Sie diese Methode, um die Schnittstelle zum übergebene Zeiger aus der globalen Schnittstellentabelle (GIT) zu kopieren.|  
|[CComGITPtr::Detach](#detach)|Rufen Sie diese Methode, um die Zuordnung aufheben, die Schnittstelle aus der `CComGITPtr` Objekt.|  
|[CComGITPtr::GetCookie](#getcookie)|Rufen Sie diese Methode, um die Rückgabegröße des aus der `CComGITPtr` Objekt.|  
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
 Objekte, die den FTM aggregieren und müssen von anderen Objekten abgerufene Schnittstellenzeiger verwenden müssen zusätzliche Schritte sicher, dass die Schnittstellen richtig gemarshallt werden. Üblicherweise gehört hierzu die Schnittstellenzeiger in der GIT speichern und die Zeiger aus der GIT jedes Mal, wenn sie verwendet wird. Die Klasse `CComGITPtr` wird bereitgestellt, damit Sie in der GIT gespeicherte Schnittstellenzeigern verwenden können.  
  
> [!NOTE]
>  Die globale Schnittstelle Tabelle-Funktion ist nur unter Windows 95 mit DCOM Version 1.1 und höher, Windows 98, Windows NT 4.0 mit Service Pack 3 oder höher und Windows 2000 verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="attach"></a>CComGITPtr::Attach  
 Rufen Sie diese Methode, um den Schnittstellenzeiger in der globalen Schnittstellentabelle (GIT) zu registrieren.  
  
```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Der Schnittstellenzeiger GIT hinzugefügt werden.  
  
 `dwCookie`  
 Das Cookie verwendet, um den Schnittstellenzeiger zu identifizieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds wird ein Assertionsfehler auftreten, wenn GIT nicht gültig ist, oder wenn das Cookie gleich NULL ist.  
  
##  <a name="ccomgitptr"></a>CComGITPtr::CComGITPtr  
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
 Ein Verweis auf einen vorhandenen `CComGITPtr` Objekt.  
  
 [in] `dwCookie`  
 Ein Cookie verwendet, um den Schnittstellenzeiger zu identifizieren.  
  
 [in] `rv`  
 Die Quelle `CComGITPtr` Objekt zum Verschieben von Daten aus.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein neues `CComGITPtr` -Objekt optional mithilfe eines vorhandenen `CComGITPtr` Objekt.  
  
 Der Konstruktor mit `rv` ist ein Verschiebungskonstruktor. Verschieben der Daten aus der Quelle `rv`, und klicken Sie dann `rv` deaktiviert ist.  
  
##  <a name="dtor"></a>CComGITPtr:: ~ CComGITPtr  
 Der Destruktor.  
  
```
~CComGITPtr() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernen Sie die Schnittstelle aus der globalen Schnittstellentabelle (GIT), mit [CComGITPtr::Revoke](#revoke).  
  
##  <a name="copyto"></a>CComGITPtr::CopyTo  
 Rufen Sie diese Methode, um die Schnittstelle zum übergebene Zeiger aus der globalen Schnittstellentabelle (GIT) zu kopieren.  
  
```
HRESULT CopyTo(T** pp) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pp`  
 Der Zeiger handelt es sich um die Schnittstelle zu empfangen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die GIT-Benutzeroberfläche wird in der übergebene Zeiger kopiert. Der Zeiger muss vom Aufrufer freigegeben werden, wenn es nicht mehr benötigt wird.  
  
##  <a name="detach"></a>CComGITPtr::Detach  
 Rufen Sie diese Methode, um die Zuordnung aufheben, die Schnittstelle aus der `CComGITPtr` Objekt.  
  
```
DWORD Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Cookie aus der `CComGITPtr` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Es obliegt dem Aufrufer, entfernen Sie die Schnittstelle aus der GIT mit [CComGITPtr::Revoke](#revoke).  
  
##  <a name="getcookie"></a>CComGITPtr::GetCookie  
 Rufen Sie diese Methode, um die Rückgabegröße des aus der `CComGITPtr` Objekt.  
  
```
DWORD GetCookie() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Cookie zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Cookie ist eine Variable, die eine Schnittstelle und den Speicherort identifiziert.  
  
##  <a name="m_dwcookie"></a>CComGITPtr::m_dwCookie  
 Das Cookie.  
  
```
DWORD m_dwCookie;
```  
  
### <a name="remarks"></a>Hinweise  
 Das Cookie wird eine Membervariable, die eine Schnittstelle und den Speicherort identifiziert.  
  
##  <a name="operator_eq"></a>CComGITPtr::operator =  
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
 Gibt den aktualisierten `CComGITPtr` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Weist einen neuen Wert zu einem `CComGITPtr` -Objekt, ein vorhandenes Objekt oder aus einem Verweis auf eine globale Schnittstellentabelle.  
  
##  <a name="operator_dword"></a>CComGITPtr::operator DWORD  
 Gibt das Cookie für die `CComGITPtr` Objekt.  
  
```  
operator DWORD() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Das Cookie ist eine Variable, die eine Schnittstelle und den Speicherort identifiziert.  
  
##  <a name="revoke"></a>CComGITPtr::Revoke  
 Rufen Sie diese Methode, um die aktuelle Schnittstelle aus der globalen Schnittstellentabelle (GIT) zu entfernen.  
  
```
HRESULT Revoke() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt die Schnittstelle aus der GIT.  
  
## <a name="see-also"></a>Siehe auch  
 [Freethreaded Marshaler](../../atl/atl-and-the-free-threaded-marshaler.md)   
 [Zugriff auf Schnittstellen hinweg](http://msdn.microsoft.com/library/windows/desktop/ms682353)   
 [Verwenden der globalen Schnittstellentabelle](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

