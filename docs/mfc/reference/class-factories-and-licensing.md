---
title: Klassenfabriken und Lizenzierung | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- class factories, and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: a8ef7ba19d2337e4e50f34d7cdd528024a1d90aa
ms.lasthandoff: 02/24/2017

---
# <a name="class-factories-and-licensing"></a>Klassenfabriken und Lizenzierung
Zum Erstellen einer Instanz des OLE-Steuerelements ruft eine Steuerelementcontainer-Anwendung eine Memberfunktion Klassenfactory des Steuerelements. Da das Steuerelement ein tatsächliches OLE-Objekt ist, ist die Klassenfactory für die Erstellung von Instanzen des Steuerelements verantwortlich. Jede Steuerelementklasse OLE benötigen eine Klassenfactory.  
  
 Eine weitere wichtige Funktion von OLE-Steuerelementen ist die Fähigkeit, eine Lizenz zu erzwingen. Assistent können Sie während der Erstellung des Steuerelementprojekts Lizenzierung zu integrieren. Weitere Informationen zu Lizenzierung, finden Sie im Artikel [ActiveX-Steuerelemente: Lizenzierung ein ActiveX-Steuerelement](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
 Die folgende Tabelle enthält einige Makros und Funktionen, die zum Deklarieren und Implementieren eines Steuerelements Klassenfactory und Lizenz des Steuerelements.  
  
### <a name="class-factories-and-licensing"></a>Klassenfabriken und Lizenzierung  
  
|||  
|-|-|  
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|Deklariert die Klassenfactory für ein OLE-Steuerelement oder eine Eigenschaft an.|  
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|Implementiert das Steuerelement `GetClassID` Funktion und eine Instanz der Klassenfactory deklariert.|  
|[BEGIN_OLEFACTORY](#begin_olefactory)|Startet die Deklaration der Lizenzierung Funktionen.|  
|[END_OLEFACTORY](#end_olefactory)|Die Deklaration der Lizenzierung Funktionen wird beendet.|  
|[AfxVerifyLicFile](#afxverifylicfile)|Überprüft, ob ein Steuerelement für die Verwendung auf einem bestimmten Computer lizenziert ist.|  
  
##  <a name="a-namedeclareolecreateexa--declareolecreateex"></a><a name="declare_olecreate_ex"></a>DECLARE_OLECREATE_EX  
 Deklariert eine Klassenfactory und die `GetClassID` -Memberfunktion der Steuerelementklasse.  
  
```   
DECLARE_OLECREATE_EX(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name der Control-Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro in der Headerdatei Steuerelement für ein Steuerelement, das keine Lizenzierung unterstützt.  
  
 Beachten Sie, dass dieses Makro den gleichen Zweck wie im folgenden Beispiel dient:  
  
 [!code-cpp[NVC_MFCAxCtl&14;](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="a-nameimplementolecreateexa--implementolecreateex"></a><a name="implement_olecreate_ex"></a>IMPLEMENT_OLECREATE_EX  
 Das Steuerelement Klassenfactory implementiert und die [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid) -Memberfunktion der Steuerelementklasse.  
  
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
 Der Name der Eigenschaft Seite Steuerelementklasse.  
  
 *external_name*  
 Der Objektname, der für Clientanwendungen verfügbar gemacht wird.  
  
 *l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8*  
 Komponenten von der Klasse **CLSID**. Weitere Informationen zu diesen Parametern finden Sie unter den Hinweisen zur [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate).  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro muss angezeigt werden, in der Implementierungsdatei für alle Control-Klasse, verwendet die `DECLARE_OLECREATE_EX` Makro oder `BEGIN_OLEFACTORY` und `END_OLEFACTORY` Makros. Der externe Name ist der Bezeichner des OLE-Steuerelements, die für andere Anwendungen verfügbar gemacht wird. Container mit diesem Namen können ein Objekt dieser Klasse Steuerelement anfordern.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="a-namebeginolefactorya--beginolefactory"></a><a name="begin_olefactory"></a>BEGIN_OLEFACTORY  
 Startet die Deklaration in der Headerdatei der Steuerelementklasse Klassenfactory.  
  
``` 
BEGIN_OLEFACTORY(class_name)  
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Gibt den Namen der Control-Klasse, deren Klassenfactory sieht folgendermaßen aus.  
  
### <a name="remarks"></a>Hinweise  
 Deklarationen von Lizenzierung Funktionen Klassenfactory sollte unmittelbar nach beginnen `BEGIN_OLEFACTORY`.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="a-nameendolefactorya--endolefactory"></a><a name="end_olefactory"></a>END_OLEFACTORY  
 Die Deklaration des Steuerelements Klassenfactory wird beendet.  
  
```  
END_OLEFACTORY(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name der Control-Klasse, deren Klassenfactory sieht folgendermaßen aus.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="a-nameafxverifylicfilea--afxverifylicfile"></a><a name="afxverifylicfile"></a>AfxVerifyLicFile  
 Mit dieser Funktion können Sie überprüfen, ob die Lizenzdatei durch den Namen `pszLicFileName` gilt für das OLE-Steuerelement.  
  
```   
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,  
    LPCTSTR  pszLicFileName,  
    LPOLESTR  pszLicFileContents,  
    UINT cch = -1); 
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 Der Instanzhandle der DLL, die das lizenzierte Steuerelement zugeordnet werden soll.  
  
 `pszLicFileName`  
 Zeigt auf eine Null-terminierte Zeichenfolge mit dem Dateinamen der Lizenz.  
  
 `pszLicFileContents`  
 Punkte in eine Bytefolge, die die Sequenz finden Sie am Anfang der Datei übereinstimmen muss.  
  
 `cch`  
 Anzahl der Zeichen im `pszLicFileContents`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Lizenzdatei vorhanden ist, und mit der Zeichenfolge in beginnt `pszLicFileContents`; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `cch` Â € ist "1, um diese Funktion verwendet:  
  
 [!code-cpp[NVC_MFC_Utilities Nr.&36;](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]  

### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

