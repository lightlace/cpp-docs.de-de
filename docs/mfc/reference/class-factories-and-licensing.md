---
title: Klassenfabriken und Lizenzierung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.classes
dev_langs: C++
helpviewer_keywords: class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 79710cb1fa67ec8315fe287364126f88b4b498d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="class-factories-and-licensing"></a>Klassenfabriken und Lizenzierung
Um eine Instanz des OLE-Steuerelements zu erstellen, ruft eine Steuerelementcontainer-Anwendung Memberfunktion einer Klassenfactory für das Steuerelement. Da das Steuerelement ein tatsächliches OLE-Objekt ist, ist die Klassenfactory für die Erstellung von Instanzen des Steuerelements verantwortlich. Jede Steuerelementklasse OLE muss eine Klassenfactory haben.  
  
 Eine weitere wichtige Funktion von OLE-Steuerelemente ist deren Fähigkeit, eine Lizenz zu erzwingen. Assistent ermöglicht Ihnen während der Erstellung des Steuerelementprojekt Lizenzierung zu integrieren. Weitere Informationen zur Lizenzierung von Steuerelement finden Sie im Artikel [ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelement](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
 Die folgende Tabelle enthält einige Makros und Funktionen, die zum Deklarieren und Implementieren des Steuerelements Klassenfactory verwendet und mit der Lizenz des Steuerelements.  
  
### <a name="class-factories-and-licensing"></a>Klassenfabriken und Lizenzierung  
  
|||  
|-|-|  
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|Deklariert das Klassenfactory für ein OLE-Steuerelements oder Eigenschaftenseite.|  
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|Des Steuerelements implementiert `GetClassID` -Funktion und eine Instanz der Klassenfactory deklariert.|  
|[BEGIN_OLEFACTORY](#begin_olefactory)|Startet die Deklaration der Lizenzierung Funktionen.|  
|[END_OLEFACTORY](#end_olefactory)|Beendet die Deklaration der Lizenzierung Funktionen.|  
|[AfxVerifyLicFile](#afxverifylicfile)|Überprüft, ob ein Steuerelement für die Verwendung auf einem bestimmten Computer lizenziert ist.|  
  
##  <a name="declare_olecreate_ex"></a>DECLARE_OLECREATE_EX  
 Deklariert eine Klassenfactory und die `GetClassID` Memberfunktion der Control-Klasse.  
  
```   
DECLARE_OLECREATE_EX(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name des der Control-Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro in der Headerdatei des Steuerelements-Klasse für ein Steuerelement, das keine Lizenzierung unterstützt.  
  
 Beachten Sie, dass dieses Makro den gleichen Zweck wie das folgende Codebeispiel dient:  
  
 [!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="implement_olecreate_ex"></a>IMPLEMENT_OLECREATE_EX  
 Das Steuerelement-Klassenfactory implementiert und die [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid) Memberfunktion der Steuerelementklasse.  
  
```   
IMPLEMENT_OLECREATE_EX(
   class_name,   
    external_name,    
    l,   
    w1,   
    w2,   
    b1,   
    b2,   
    b3,   
    b4,   
    b5,   
    b6,   
    b7,
    b8)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name der Seite der Steuerelementklasse-Eigenschaft.  
  
 *external_name*  
 Der Objektname, der für Anwendungen verfügbar gemacht wird.  
  
 *l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8*  
 Komponenten von der Klasse **CLSID**. Weitere Informationen zu diesen Parametern finden Sie unter den Hinweisen für [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate).  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro muss angezeigt werden, in der Implementierungsdatei für alle Control-Klasse, verwendet der `DECLARE_OLECREATE_EX` Makro oder die `BEGIN_OLEFACTORY` und `END_OLEFACTORY` Makros. Der externe Name ist der Bezeichner des OLE-Steuerelements, das für andere Anwendungen verfügbar gemacht wird. Container mit diesem Namen können Sie ein Objekt dieser Klasse Control anfordern.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="begin_olefactory"></a>BEGIN_OLEFACTORY  
 Startet die Deklaration von Klassenfactory in der Headerdatei der Steuerelementklasse an.  
  
``` 
BEGIN_OLEFACTORY(class_name)  
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Gibt den Namen der Steuerelementklasse, deren Klassenfactory, dies ist.  
  
### <a name="remarks"></a>Hinweise  
 Deklarationen von Funktionen Lizenzierung Klassenfactory sofort nach dem beginnen soll `BEGIN_OLEFACTORY`.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="end_olefactory"></a>END_OLEFACTORY  
 Beendet die Deklaration von Klassenfactory des Steuerelements an.  
  
```  
END_OLEFACTORY(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name der Steuerelementklasse, deren Klassenfactory, dies ist.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="afxverifylicfile"></a>AfxVerifyLicFile  
 Mit dieser Funktion können Sie überprüfen, ob die Datei des License benannten `pszLicFileName` gilt für die OLE-Steuerelements.  
  
```   
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,  
    LPCTSTR  pszLicFileName,  
    LPOLESTR  pszLicFileContents,  
    UINT cch = -1); 
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 Der Instanzhandle, der DLL, die das lizenzierte Steuerelement zugeordnet werden soll.  
  
 `pszLicFileName`  
 Verweist auf eine Null-terminierte Zeichenfolge, enthält der Dateiname der Lizenz.  
  
 `pszLicFileContents`  
 Verweist auf eine Bytesequenz, die die Sequenz, die am Anfang der Lizenzdatei gefunden entsprechen muss.  
  
 `cch`  
 Anzahl der Zeichen in `pszLicFileContents`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Datei des License vorhanden ist, und mit der Zeichenfolge im beginnt `pszLicFileContents`, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `cch` ist-1, diese Funktion verwendet:  
  
 [!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]  

### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
