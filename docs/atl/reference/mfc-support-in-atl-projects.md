---
title: "MFC-Unterst&#252;tzung in ATL-Projekten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "vc.atl.addmfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, MFC-Unterstützung"
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-Unterst&#252;tzung in ATL-Projekten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie im ATL\-Projekt\-Assistenten **MFC unterstützen** auswählen, wird die Anwendung vom Projekt als MFC\-Anwendungsobjekt \(Klasse\) deklariert.  Das Projekt initialisiert die MFC\-Bibliothek und instanziiert eine Klasse \(*ProjName*\-Klasse\), die von [CWinApp](../../mfc/reference/cwinapp-class.md) abgeleitet ist.  
  
 Diese Option ist nur für nicht attributierte ATL\-DLL\-Projekte verfügbar.  
  
```  
class CProjNameApp : public CWinApp  
{  
public:  
  
// Overrides  
   virtual BOOL InitInstance();  
   virtual int ExitInstance();  
   DECLARE_MESSAGE_MAP()  
};  
  
BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)  
END_MESSAGE_MAP()  
  
CProjNameApp theApp;  
  
BOOL CProjNameApp::InitInstance()  
{  
   return CWinApp::InitInstance();  
}  
  
int CProjNameApp::ExitInstance()  
{  
   return CWinApp::ExitInstance();  
}  
```  
  
 Sie können die Anwendungsobjektklasse und ihre Funktionen `InitInstance` und `ExitInstance` in der Klassenansicht anzeigen.  
  
## Siehe auch  
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)   
 [Standardmäßige ATL\-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)