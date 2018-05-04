---
title: MFC-Unterstützung in ATL-Projekte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.addmfc
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d42afec863695b1cab05c2d3cf2f65f3d64a1507
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

