---
title: MFC-Unterstützung in ATL-Projekte
ms.date: 11/04/2016
f1_keywords:
- vc.atl.addmfc
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
ms.openlocfilehash: 0aece6805f1de987b0164f405e50b99fd706fef4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275424"
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
