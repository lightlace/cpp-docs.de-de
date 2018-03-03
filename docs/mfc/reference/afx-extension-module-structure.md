---
title: AFX_EXTENSION_MODULE-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b4ac896fb16aa3c338cadd6273e226eebe986ae7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="afxextensionmodule-structure"></a>AFX_EXTENSION_MODULE-Struktur
Die `AFX_EXTENSION_MODULE` wird während der Initialisierung des MFC-Erweiterungs-DLLs verwendet, um den Status des MFC-Erweiterungs-DLL-Modul zu speichern.  
  
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
 **"True"** , wenn die DLL-Modul mit initialisiert wurde `AfxInitExtensionModule`.  
  
 `hModule`  
 Gibt das Handle für das DLL-Modul an.  
  
 *hResource*  
 Gibt das Handle für das benutzerdefinierte Ressourcenmodul DLL an.  
  
 *pFirstSharedClass*  
 Ein Zeiger auf Informationen (die `CRuntimeClass` Struktur) zum ersten Laufzeitklasse in das DLL-Modul. Wird verwendet, um den Anfang der Liste der Common Language Runtime-Klasse bereitzustellen.  
  
 *pFirstSharedFactory*  
 Ein Zeiger auf die erste Objektfactory das DLL-Modul (ein `COleObjectFactory` Objekt). Wird verwendet, um den Anfang der Liste der Factory bereitzustellen.  
  
## <a name="remarks"></a>Hinweise  
 MFC-Erweiterungs-DLLs müssen zwei Dinge in ihre `DllMain` Funktion:  
  
-   Rufen Sie [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) und überprüfen den Rückgabewert.  
  
-   Erstellen einer **CDynLinkLibrary** Objekt, wenn die DLL exportieren [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Objekte oder verfügt über eine eigene benutzerdefinierte Ressourcen.  
  
 Die `AFX_EXTENSION_MODULE` Struktur dient zum Speichern einer Kopie der MFC-Erweiterungs-DLL-Modulstatus, einschließlich einer Kopie der Objekte der Common Language Runtime-Klasse, die von der MFC-Erweiterungs-DLL, im Rahmen des normalen statische Objektkonstruktion ausgeführt initialisiert wurden, bevor `DllMain` ist eingegeben. Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 Die Modulinformationen gespeichert, der `AFX_EXTENSION_MODULE` Struktur kopiert werden kann, in der **CDynLinkLibrary** Objekt. Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)   
 [AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)

