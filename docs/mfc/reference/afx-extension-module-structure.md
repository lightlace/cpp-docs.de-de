---
title: "AFX_EXTENSION_MODULE-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "AFX_EXTENSION_MODULE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_EXTENSION_MODULE-Struktur"
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# AFX_EXTENSION_MODULE-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`AFX_EXTENSION_MODULE` wird während der Initialisierung von MFC\-Erweiterungs\-DLLs verwendet, um den Zustand des Erweiterungs\-DLL\-Moduls aufzunehmen.  
  
## Syntax  
  
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
  
#### Parameter  
 *bInitialized*  
 **TRUE**, wenn das DLL\-Modul mit `AfxInitExtensionModule` initialisiert wurde.  
  
 `hModule`  
 Gibt dem Handle des DLL\-Moduls an.  
  
 *hResource*  
 Gibt dem Handle des benutzerdefinierten Ressourcenmoduls der DLL an.  
  
 *pFirstSharedClass*  
 Ein Zeiger zu Informationen die Struktur \( `CRuntimeClass` \) zur ersten Laufzeitklasse des DLL\-Moduls.  Wird verwendet, um den Start der Ablaufklassenliste bereitzustellen.  
  
 *pFirstSharedFactory*  
 Ein Zeiger auf das DLL\-Modul Objekt zuerst Factory ein \(ein `COleObjectFactory`\-Objekt\).  Wird verwendet, um den Start der Klassenfactoryliste bereitzustellen.  
  
## Hinweise  
 MFC\-Erweiterungs\-DLL\-Anforderung, zwei Dinge in ihrem `DllMain` auszuführen arbeiten:  
  
-   Rufen Sie [AfxInitExtensionModule](../Topic/AfxInitExtensionModule.md) auf und überprüfen Sie den Rückgabewert.  
  
-   Erstellen Sie ein **CDynLinkLibrary**\-Objekt, wenn die DLL [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekte exportieren oder eigene benutzerdefinierten Ressourcen hat.  
  
 Die `AFX_EXTENSION_MODULE`\-Struktur wird verwendet, um eine Kopie des Erweiterungs\-DLL\-Modulzustandes, einschließlich einer Kopie der Ablaufklassenobjekte enthalten, die von der Erweiterungs\-DLL als Teil der normalen statischen ausgeführten Objektkonstruktion initialisiert wurden, bevor `DllMain` eingegeben wird.  Beispiel:  
  
 [!CODE [NVC_MFC_DLL#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_DLL#2)]  
  
 Die Modulinformationen, die in der `AFX_EXTENSION_MODULE`\-Struktur gespeichert werden, können in das Objekt **CDynLinkLibrary** kopiert werden.  Beispiel:  
  
 [!CODE [NVC_MFC_DLL#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_DLL#5)]  
  
## Anforderungen  
 **Header:** afx.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](../Topic/AfxInitExtensionModule.md)   
 [AfxTermExtensionModule](../Topic/AfxTermExtensionModule.md)