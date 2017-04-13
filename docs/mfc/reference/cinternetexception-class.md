---
title: CInternetException Klasse | Microsoft Docs
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
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: 1831f868b7388cbc6382e26fca92280c3b880276
ms.lasthandoff: 04/12/2017

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
|[CInternetException::m_dwContext](#m_dwcontext)|Den zugeordneten Kontextwert durch den Vorgang, der die Ausnahme verursacht hat.|  
|[CInternetException::m_dwError](#m_dwerror)|Der Fehler, der die Ausnahme verursacht hat.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CInternetException` Klasse enthält zwei öffentliche Datenmember: eine enthält den Fehlercode, der der Ausnahme zugeordnet, und der andere enthält den Kontextbezeichner des Internet-Anwendung, die dem Fehler zugeordnet.  
  
 Weitere Informationen zu Kontext-IDs für Internet-Anwendungen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cinternetexception"></a>CInternetException::CInternetException  
 Diese Memberfunktion wird aufgerufen, wenn ein `CInternetException` Objekt erstellt wird.  
  
```  
CInternetException(DWORD dwError);
```  
  
### <a name="parameters"></a>Parameter  
 `dwError`  
 Der Fehler, der die Ausnahme verursacht hat.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Auslösen einer CInternetException die globale MFC-Funktion [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).  
  
##  <a name="m_dwcontext"></a>CInternetException::m_dwContext  
 Der Kontextwert verwandte internetvorgang zugeordnet.  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Kontextbezeichner wird ursprünglich in angegeben [CInternetSession](../../mfc/reference/cinternetsession-class.md) und übergeben von MFC ermöglicht, [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- und [CInternetFile](../../mfc/reference/cinternetfile-class.md)-abgeleitete Klassen. Sie können diesen Standardwert überschreiben und Zuweisen von `dwContext` Parameter einen Wert Ihrer Wahl. `dwContext`Jeder Vorgang, der das angegebene Objekt zugeordnet ist. `dwContext`identifiziert den Vorgang vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
##  <a name="m_dwerror"></a>CInternetException::m_dwError  
 Der Fehler, der die Ausnahme verursacht hat.  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Fehlerwert kann ein System sein Fehlercode in WINERROR gefunden. H oder einen Fehlerwert aus WININET. H.  
  
 Eine Liste der Win32-Fehlercodes, finden Sie unter [Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms681381). Eine Liste der Internet-spezifische Fehlermeldungen finden Sie unter. Beide Themen sind in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)

