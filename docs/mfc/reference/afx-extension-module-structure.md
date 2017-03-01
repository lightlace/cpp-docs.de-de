---
title: AFX_EXTENSION_MODULE-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
caps.latest.revision: 11
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: f2699316266e9cc061fa898c4176e36ae8323b33
ms.lasthandoff: 02/24/2017

---
# <a name="afxextensionmodule-structure"></a>AFX_EXTENSION_MODULE-Struktur
Der `AFX_EXTENSION_MODULE` wird während der Initialisierung der Erweiterung der MFC-DLLs verwendet, um den Status der Erweiterung DLL-Modul zu halten.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct AFX_EXTENSION_MODULE  
{  
    BOOL bInitialized;  
    HMODULE hModule;  
    HMODULE hResource;  
    CRuntimeClass* pFirstSharedClass;  
    COleObjectFactory* pFirstSharedFactory;  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 *bInitialized*  
 **True,** Wenn das DLL-Modul initialisiert wurde, mit `AfxInitExtensionModule`.  
  
 `hModule`  
 Gibt das Handle für das DLL-Modul an.  
  
 *hResource*  
 Gibt das Handle des Moduls benutzerdefinierte Ressourcen-DLL.  
  
 *pFirstSharedClass*  
 Ein Zeiger auf Informationen (die `CRuntimeClass` Struktur) zur ersten Laufzeitklasse das DLL-Modul. Wird verwendet, um den Anfang der Liste der Common Language Runtime bereitzustellen.  
  
 *pFirstSharedFactory*  
 Ein Zeiger auf das erste Objekt-Factory das DLL-Modul (ein `COleObjectFactory` Objekt). Wird verwendet, um den Anfang der Liste der Factory bereitzustellen.  
  
## <a name="remarks"></a>Hinweise  
 MFC-Erweiterungs-DLLs müssen zwei Dinge in ihren `DllMain` Funktion:  
  
-   Rufen Sie [AfxInitExtensionModule](http://msdn.microsoft.com/library/15f0c820-ff34-4da6-8077-79afbbb8dac1) , und überprüfen Sie den Rückgabewert.  
  
-   Erstellen einer **CDynLinkLibrary** Objekt, wenn die DLL exportieren [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Objekte oder verfügt über eine eigene benutzerdefinierte Ressourcen.  
  
 Die `AFX_EXTENSION_MODULE` -Struktur verwendet, um eine Kopie der Erweiterung DLL Modulstatus, einschließlich einer Kopie der Objekte der Common Language Runtime-Klasse, die als Teil der normalen statische Objektkonstruktion ausgeführt, bevor mit der Erweiterung DLL initialisiert wurden `DllMain` eingegeben wird. Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_DLL&#2;](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 Die Modulinformationen aus der `AFX_EXTENSION_MODULE` Struktur kopiert werden kann, in der **CDynLinkLibrary** Objekt. Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_DLL&5;](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](http://msdn.microsoft.com/library/15f0c820-ff34-4da6-8077-79afbbb8dac1)   
 [AfxTermExtensionModule](http://msdn.microsoft.com/library/b64de402-f1e3-4c26-9823-08c07876aaaa)


