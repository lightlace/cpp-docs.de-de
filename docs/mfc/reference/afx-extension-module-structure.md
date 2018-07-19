---
title: AFX_EXTENSION_MODULE-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65f1f2a6416ef93395f7ec73b27a89bf44e2d885
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339383"
---
# <a name="afxextensionmodule-structure"></a>AFX_EXTENSION_MODULE-Struktur
Die `AFX_EXTENSION_MODULE` wird während der Initialisierung des MFC-Erweiterungs-DLLs verwendet, um den Status der MFC-Erweiterungs-DLL-Modul zu speichern.  
  
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
 TRUE, wenn die DLL-Modul mit initialisiert wurde `AfxInitExtensionModule`.  
  
 *hModule*  
 Gibt das Handle des DLL-Moduls.  
  
 *hResource*  
 Gibt das Handle für das benutzerdefinierte Ressourcenmodul DLL an.  
  
 *pFirstSharedClass*  
 Ein Zeiger auf die Informationen (die `CRuntimeClass` Struktur) über das DLL-Modul erste Common Language Runtime-Klasse. Wird verwendet, um den Anfang der Liste der Laufzeit bereitzustellen.  
  
 *pFirstSharedFactory*  
 Ein Zeiger auf das erste Objekt-Factory das DLL-Modul (eine `COleObjectFactory` Objekt). Wird verwendet, um den Anfang der Liste der Factory bereitzustellen.  
  
## <a name="remarks"></a>Hinweise  
 MFC-Erweiterungs-DLLs müssen zwei Dinge in ihre `DllMain` Funktion:  
  
-   Rufen Sie [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) und den Rückgabewert überprüfen.  
  
-   Erstellen Sie eine `CDynLinkLibrary` Objekt, wenn die DLL exportieren [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Objekte oder verfügt über eine eigene benutzerdefinierte Ressourcen.  
  
 Die `AFX_EXTENSION_MODULE` Struktur wird zum Speichern einer Kopie der MFC-Erweiterungs-DLL-Modulstatus, einschließlich einer Kopie der Objekte der Common Language Runtime-Klasse, die als Teil der normal statische Objektkonstruktion ausgeführt, bevor von den MFC-Erweiterungs-DLL initialisiert wurden `DllMain` ist eingegeben. Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 Die Modulinformationen aus der `AFX_EXTENSION_MODULE` Struktur kopiert werden kann, in der `CDynLinkLibrary` Objekt. Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)   
 [AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)

