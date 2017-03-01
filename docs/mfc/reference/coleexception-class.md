---
title: "COleException verfügt Klasse | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleException
dev_langs:
- C++
helpviewer_keywords:
- COleException class
- exceptions, OLE
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 059c92c8dc8796cf103cc02533ba5f3526720249
ms.lasthandoff: 02/24/2017

---
# <a name="coleexception-class"></a>COleException verfügt-Klasse
Stellt eine Ausnahmebedingung dar, die sich auf einen OLE-Vorgang bezieht.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleException : public CException  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleException::Process](#process)|Übersetzt eine abgefangene Ausnahme in ein OLE-Rückgabecode.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|Enthält den Status, der die Ursache der Ausnahme angibt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COleException` -Klasse enthält einen öffentlichen Datenmember, der den Statuscode, die die Ursache für die Ausnahme enthält.  
  
 Im Allgemeinen erstellen Sie keine `COleException` -Objekt direkt, sondern, rufen Sie [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Weitere Informationen über Ausnahmen finden Sie in den Artikeln [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: OLE-Ausnahmen](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="a-namemsca--coleexceptionmsc"></a><a name="m_sc"></a>COleException::m_sc  
 Dieses Datenelement enthält OLE-Statuscode, der den Grund für die Ausnahme angibt.  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Wert dieser Variablen wird festgelegt, indem [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Weitere Informationen zu `SCODE`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#22;](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="a-nameprocessa--coleexceptionprocess"></a><a name="process"></a>COleException::Process  
 Rufen Sie die **Prozess** Memberfunktion, die eine abgefangene Ausnahme in ein OLE-Statuscode zu übersetzen.  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>Parameter  
 *pAnyException*  
 Ein Zeiger auf eine abgefangene Ausnahme.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein OLE-Statuscode.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Funktion ist **statische**.  
  
 Weitere Informationen zu `SCODE`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CALCDRIV](../../visual-cpp-samples.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




