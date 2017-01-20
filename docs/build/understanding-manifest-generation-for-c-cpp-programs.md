---
title: "Manifestgenerierung f&#252;r C/C++-Programme"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Manifeste [C++]"
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Manifestgenerierung f&#252;r C/C++-Programme
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein [Manifest](http://msdn.microsoft.com/library/aa375365) ist ein XML\-Dokument, das entweder als externe XML\-Datei vorliegt oder als Ressource in einer Anwendung oder Assembly eingebettet ist.  Das Manifest einer [isolierten Anwendung](http://msdn.microsoft.com/library/aa375190) wird zur Verwaltung der Namen und Versionen freigegebener paralleler Assemblys verwendet, an die die Anwendung zur Laufzeit gebunden werden muss.  Das Manifest einer [parallelen Assembly](_win32_side_by_side_assemblies) gibt deren Abhängigkeiten von Namen, Versionen, Ressourcen sowie anderen Assemblys an.  
  
 Es gibt zwei Möglichkeiten, für eine isolierte Anwendung oder eine parallele Assembly ein Manifest zu erstellen.  Zum einen kann der Entwickler der Assembly manuell eine Manifestdatei erstellen, die den Regeln und Namenskonventionen entspricht.  Alternativ kann der Linker automatisch ein Manifest generieren, wenn ein Programm nur von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Assemblys wie CRT, MFC, ATL oder anderen abhängig ist.  
  
 Die Header von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken enthalten Assemblyinformationen. Wenn diese Bibliotheken in den Anwendungscode eingeschlossen werden, werden diese Assemblyinformationen vom Linker zum Erstellen eines Manifests für die endgültige Binärdatei verwendet.  Der Linker bettet die Manifestdatei nicht in die Binärdatei ein, er kann das Manifest nur als externe Datei generieren.  Ein Manifest in Form einer externen Datei kann möglicherweise nicht in allen Szenarios verwendet werden.  So wird z. B. empfohlen, dass private Assemblys über eingebettete Manifeste verfügen.  Mithilfe des Manifesttools kann ein Manifest auch in ein mit nmake erstelltes Befehlszeilenbuild eingebettet werden. Weitere Informationen finden Sie unter [Manifestgenerierung über die Befehlszeile](../build/manifest-generation-at-the-command-line.md).  Beim Erstellen in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] kann ein Manifest eingebettet werden, indem im Dialogfeld **Projekteigenschaften** eine Eigenschaft für das Manifesttool festgelegt wird. Weitere Informationen finden Sie unter [Manifestgenerierung in Visual Studio](../build/manifest-generation-in-visual-studio.md).  
  
## Siehe auch  
 [Konzept der isolierten Anwendungen und der parallelen Assemblys](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Erstellen von isolierten Anwendungen und parallelen Assemblys \(C\/C\+\+\)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)