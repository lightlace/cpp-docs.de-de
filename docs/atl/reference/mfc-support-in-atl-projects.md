---
title: "MFC-Unterstützung in ATL-Projekte | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.atl.addmfc
dev_langs: C++
helpviewer_keywords: ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 399f9fcea216adf5480bf38b8aba051c60eed496
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-support-in-atl-projects"></a>MFC-Unterstützung in ATL-Projekte
Bei Auswahl des **MFC unterstützen** im ATL-Projekt-Assistenten Ihrem Projekt die Anwendung als ein MFC-Anwendungsobjekt (Klasse) deklariert. Das Projekt initialisiert die MFC-Bibliothek und instanziiert die Klasse (Klasse *ProjName*), stammt aus [CWinApp](../../mfc/reference/cwinapp-class.md).  
  
 Diese Option ist nicht attributierte ATL-DLL nur für Projekte verfügbar.  
  
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
  
 Sie können die Anwendungsobjektklasse anzeigen und die zugehörige `InitInstance` und `ExitInstance` Funktionen in der Klassenansicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)   
 [Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)

