---
title: "&#196;ndern des Laufzeitverhaltens eines Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], Laufzeitverhalten"
ms.assetid: 78b44b0f-0d5a-4da0-8aa2-595f5789c634
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# &#196;ndern des Laufzeitverhaltens eines Steuerelements
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie [ein Steuerelement eingefügt](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md) und mindestens eine [Wrapperklasse](../../data/ado-rdo/wrapper-classes.md) generiert haben, können Sie die Methoden des Steuerelements aufrufen und die Ereignishandler des Steuerelements programmieren.  
  
 Die [Wrapperklassen](../../data/ado-rdo/wrapper-classes.md) des Steuerelements geben die Funktionen an, mit denen Sie die das Laufzeitverhalten des Steuerelements ändern können. Fügen Sie die Headerdatei der entsprechenden Wrapperklasse ein, und verwenden Sie die Methoden. Um eine Eigenschaft festzulegen, suchen Sie nach einer Accessormethode, die den Namen der Eigenschaft und das Präfix „Set“ hat. Um eine Eigenschaft abzurufen, suchen Sie nach einer Accessormethode, die den Namen der Eigenschaft und das Präfix „Get“ hat. Ereignishandler können später geschrieben werden.  
  
 Da die Steuerelemente über Automatisierung implementiert werden, können nur automatisierungssichere Typen wie BSTR und VARIANT übergeben werden. Zwar können Sie Systemaufrufe verwenden, um BSTRs und VARIANTs zuzuordnen und festzulegen, es bietet sich aber an, die ATL\-Wrapperklassen verwenden möchten \([CComBSTR](../../atl/reference/ccombstr-class.md), [CComVariant](../../atl/reference/ccomvariant-class.md)\), die Visual C\+\+\-Compiler\-COM\-Unterstützungswrapperklassen \([\_bstr\_t](../../cpp/bstr-t-class.md), [\_variant\_t](../../cpp/variant-t-class.md)\) oder die MFC\-Wrapperklasse \([COleVariant](../../mfc/reference/colevariant-class.md)\) zu verwenden.  
  
 Wenn Sie ein Steuerelement hinzufügen, generiert der Assistent zum Einfügen von ActiveX\-Steuerelementen Wrapperklassen für die Co\-Klassen des Steuerelements, die dessen interne Datenobjekte verwalten. Diese Klassen umfassen nicht alle Elemente von RDO\-oder ADO, sondern entsprechen internen Objekten, die in der Typbibliothek deklariert sind.  
  
 Wenn Sie ADO und RDO direkt verwenden möchten, müssen Sie direkt eine Verbindung mit den ADO\- oder RDO\-DLLs \(„Msado15.dll“ oder „Msrdo20.dll“\) herstellen, entweder über die [Compiler\-COM\-Unterstützungsklassen](../../cpp/compiler-com-support-classes.md), die die [\#import\-Direktive](../../preprocessor/preprocessor-directives.md) unterstützen, oder über das entsprechende SDK.  
  
## So legen Sie Steuerelementeigenschaften zur Laufzeit fest  
 Beachten Sie, dass einige Eigenschaften eines ActiveX\-Steuerelements zur Laufzeit möglicherweise schreibgeschützt sind, wodurch eine dynamische Erstellung schwierig wird. Sie können für eine Eigenschaftsinitialisierung temporär den Entwurfsmodus simulieren, indem Sie den [OnAmbientPropertyChange](../Topic/COleControl::OnAmbientPropertyChange.md)\-Handler des Steuerelementcontainers überschreiben, wie dies im Knowledge Base\-Artikel „How to: Set ActiveX Control Design\-Time Properties at Run Time \(Q260744\)“ beschrieben ist. Sie finden Knowledge Base\-Artikel unter [http:\/\/support.microsoft.com\/](http://support.microsoft.com/).  
  
## Siehe auch  
 [Verwenden von ActiveX\-Steuerelementen](../../data/ado-rdo/using-activex-controls.md)