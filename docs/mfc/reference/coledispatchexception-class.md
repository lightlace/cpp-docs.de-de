---
title: COleDispatchException Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed492198c5c667fa1ffadcaa9a3bcc0461c16d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373385"
---
# <a name="coledispatchexception-class"></a>COleDispatchException-Klasse
Behandelt Ausnahmen, die für die `IDispatch` -OLE-Schnittstelle (eine Schlüsselkomponente der OLE-Automatisierung) spezifisch sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDispatchException : public CException  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|Der Hilfekontext für Fehler.|  
|[COleDispatchException::m_strDescription](#m_strdescription)|Verbale fehlerbeschreibung.|  
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|Die Hilfedatei für die Verwendung mit `m_dwHelpContext`.|  
|[COleDispatchException::m_strSource](#m_strsource)|Anwendung, die die Ausnahme generiert hat.|  
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-Fehlercode.|  
  
## <a name="remarks"></a>Hinweise  
 Wie die anderen Ausnahmeklassen abgeleitet der `CException` Basisklasse, `COleDispatchException` kann verwendet werden, mit der **AUSLÖSEN**, `THROW_LAST`, **versuchen**, **CATCH**, `AND_CATCH`, und `END_CATCH` Makros.  
  
 Sie sollten im Allgemeinen Aufrufen [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) zu erstellen und Auslösen einer `COleDispatchException` Objekt.  
  
 Weitere Informationen zu Ausnahmen finden Sie in den Artikeln [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: OLE-Ausnahmen](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleDispatchException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="m_dwhelpcontext"></a>  COleDispatchException::m_dwHelpContext  
 Identifiziert einen Hilfekontext in der Hilfe von Ihrer Anwendung (. HLP)-Datei.  
  
```  
DWORD m_dwHelpContext;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Member wird von der Funktion festgelegt [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) Wenn eine Ausnahme ausgelöst wird.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleDispatchDriver:: CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_strdescription"></a>  COleDispatchException::m_strDescription  
 Enthält eine fehlerbeschreibung verbale wie "Der Datenträger ist voll."  
  
```  
CString m_strDescription;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Member wird von der Funktion festgelegt [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) Wenn eine Ausnahme ausgelöst wird.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleDispatchDriver:: CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_strhelpfile"></a>  COleDispatchException::m_strHelpFile  
 Das Framework füllt diese Zeichenfolge mit dem Namen der Hilfedatei für die Anwendung aus.  
  
```  
CString m_strHelpFile;  
```  
  
##  <a name="m_strsource"></a>  COleDispatchException::m_strSource  
 Das Framework füllt diese Zeichenfolge mit dem Namen der Anwendung, die die Ausnahme generiert hat.  
  
```  
CString m_strSource;  
```  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleDispatchDriver:: CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_wcode"></a>  COleDispatchException::m_wCode  
 Enthält einen Fehlercode für Ihre Anwendung spezifisch sind.  
  
```  
WORD m_wCode;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Member wird von der Funktion festgelegt [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) Wenn eine Ausnahme ausgelöst wird.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CALCDRIV](../../visual-cpp-samples.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDispatchDriver-Klasse](../../mfc/reference/coledispatchdriver-class.md)   
 [COleException-Klasse](../../mfc/reference/coleexception-class.md)
