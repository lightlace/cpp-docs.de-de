---
title: MFC-Unterstützung in ATL-Projekte | Microsoft-Dokumentation
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
ms.openlocfilehash: f3853bbe90757563f6c7dc2c9003ed7c5f2a98dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065438"
---
# <a name="mfc-support-in-atl-projects"></a>MFC-Unterstützung in ATL-Projekte

Bei Auswahl von **MFC unterstützen** im ATL-Projekt-Assistenten Ihrem Projekt die Anwendung als MFC-Anwendungsobjekt (Klasse) deklariert. Das Projekt die MFC-Bibliothek initialisiert und instanziiert die Klasse (Klasse *ProjName*), ergibt sich aus [CWinApp](../../mfc/reference/cwinapp-class.md).

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

Sehen Sie die Anwendung-Objektklasse und die zugehörige `InitInstance` und `ExitInstance` Funktionen in der Klassenansicht.

## <a name="see-also"></a>Siehe auch

[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)<br/>
[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)<br/>
[Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)

