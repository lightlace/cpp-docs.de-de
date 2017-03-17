---
title: Klasse CInternetException | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
dev_langs:
- C++
helpviewer_keywords:
- exception handling, Internet operations
- exceptions, Internet
- CInternetException class
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a128095cfc443f0ea8de4cb4028b903929a83f47
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetexception-class"></a>CInternetException-Klasse
Stellt eine Ausnahmebedingung dar, die sich auf einen Internetvorgang bezieht.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CInternetException : public CException  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetException::CInternetException](#cinternetexception)|Erstellt ein `CInternetException`-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetException::m_dwContext](#m_dwcontext)|Der Kontextwert der Vorgang, der die Ausnahme verursacht hat.|  
|[CInternetException::m_dwError](#m_dwerror)|Der Fehler, der die Ausnahme verursacht hat.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CInternetException` Klasse enthält zwei öffentliche Datenmember: eine enthält den Fehlercode der Ausnahme zugeordnet, und der andere enthält den Kontextbezeichner der Internet-Anwendung, die mit dem Fehler zugeordnet ist.  
  
 Weitere Informationen zu Kontext-IDs für Internet Applications, finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cinternetexception"></a>CInternetException::CInternetException  
 Diese Member-Funktion wird aufgerufen, wenn ein `CInternetException` Objekt erstellt wird.  
  
```  
CInternetException(DWORD dwError);
```  
  
### <a name="parameters"></a>Parameter  
 `dwError`  
 Der Fehler, der die Ausnahme verursacht hat.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Auslösen einer CInternetException die globale MFC-Funktion [AfxThrowInternetException](http://msdn.microsoft.com/library/c9645b10-9541-48b2-8b0c-94ca33fed3cb).  
  
##  <a name="m_dwcontext"></a>CInternetException::m_dwContext  
 Der Kontextwert der zugehörigen Internet-Vorgang.  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Kontext-ID wird in ursprünglich angegeben [CInternetSession](../../mfc/reference/cinternetsession-class.md) und übergeben von MFC [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- und [CInternetFile](../../mfc/reference/cinternetfile-class.md)-abgeleitete Klassen. Sie können diese Standardeinstellung außer Kraft setzen und Zuweisen von `dwContext` Parameter einen Wert Ihrer Wahl. `dwContext`Jeder Vorgang, der dem angegebenen Objekt zugeordnet ist. `dwContext`identifiziert den Vorgang vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
##  <a name="m_dwerror"></a>CInternetException::m_dwError  
 Der Fehler, der die Ausnahme verursacht hat.  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Fehlerwert ist ein System, Fehlercode in WINERROR gefunden. H oder einen Fehlerwert aus WININET. H.  
  
 Eine Übersicht über die Win32-Fehlercodes finden Sie unter [Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms681381). Eine Liste der Internet-spezifische Fehlermeldungen angezeigt werden finden Sie unter. Beide Themen werden in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)

