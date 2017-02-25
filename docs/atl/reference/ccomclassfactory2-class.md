---
title: "CComClassFactory2 Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComClassFactory2<license>"
  - "CComClassFactory2"
  - "ATL.CComClassFactory2<license>"
  - "ATL::CComClassFactory2"
  - "ATL.CComClassFactory2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactory2 class"
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComClassFactory2 Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert die Schnittstelle [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720).  
  
## Syntax  
  
```  
  
      template <  
   class license  
>  
class CComClassFactory2 : public IClassFactory2,  
   public CComObjectRootEx<CComGlobalsThreadModel>,  
   public license  
```  
  
#### Parameter  
 *Lizenz*  
 Eine Klasse, die die folgenden statischen Funktionen implementiert:  
  
-   **static BOOL VerifyLicenseKey\( BSTR**  `bstr`\);  
  
-   **static BOOL GetLicenseKey\( DWORD**  `dwReserved` **, BSTR\***  `pBstr`\);  
  
-   **statisches BOOL IsLicenseValid\( \);**  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComClassFactory2::CreateInstance](../Topic/CComClassFactory2::CreateInstance.md)|Erstellt ein Objekt des angegebenen CLSID.|  
|[CComClassFactory2::CreateInstanceLic](../Topic/CComClassFactory2::CreateInstanceLic.md)|Erstellen eines Lizenzschlüssel angegeben, erstellt ein Objekt des angegebenen CLSID.|  
|[CComClassFactory2::GetLicInfo](../Topic/CComClassFactory2::GetLicInfo.md)|Ruft die Informationen ab, die die Lizenzierungsfunktionen der Class Factory beschreiben.|  
|[CComClassFactory2::LockServer](../Topic/CComClassFactory2::LockServer.md)|Sperrt die Klassenfactory im Arbeitsspeicher.|  
|[CComClassFactory2::RequestLicKey](../Topic/CComClassFactory2::RequestLicKey.md)|Erstellt und gibt einen Lizenzschlüssel zurück.|  
  
## Hinweise  
 `CComClassFactory2` [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) implementiert die Schnittstelle, die eine Erweiterung von [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) ist.  **IClassFactory2**\-Steuerelemente gelten Erstellung durch eine Lizenz ein.  Eine Klassenfactory, die auf einem Computer lizenzierten ausführt, kann einen Ablauflizenzschlüssel bereitstellen.  Dieser Lizenzschlüssel ermöglicht es einer Anwendung, Objekte zu instanziieren, wenn eine vollständige Compute Lizenz nicht vorhanden ist.  
  
 ATL\-Objekte rufen normalerweise eine Klassenfactory ab, indem von [CComCoClass](../../atl/reference/ccomcoclass-class.md) berechnen.  Diese Klasse enthält das Makro [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md), das [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als Standardklassenfactory deklariert.  Um `CComClassFactory2` zu verwenden, geben Sie die [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md)\-Makro in der Klassendefinition des Objekts an.  Beispiel:  
  
 [!CODE [NVC_ATL_COM#2](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#2)]  
  
 **CMyLicense**, der Vorlagenparameter zu `CComClassFactory2`, muss die statischen Funktionen `VerifyLicenseKey`, `GetLicenseKey` und `IsLicenseValid` implementieren.  Im folgenden Beispiel einer einfachen Lizenzklasse:  
  
 [!CODE [NVC_ATL_COM#3](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#3)]  
  
 `CComClassFactory2` abgeleitet von **CComClassFactory2Base** und *von Lizenz*.  **CComClassFactory2Base** berechnet wiederum von **IClassFactory2** und von **CComObjectRootEx\< CComGlobalsThreadModel \>**.  
  
## Vererbungshierarchie  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComClassFactoryAutoThread Class](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComClassFactorySingleton Class](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)