---
title: Erstellen isolierter C/C++-Anwendungen
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: e02fec4115d328dd8230d68ddb65b380ec743dc0
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815202"
---
# <a name="building-cc-isolated-applications"></a>Erstellen isolierter C/C++-Anwendungen

Eine isolierte Anwendung hängt nur von Seite-an-Seite-Assemblys und bindet an seine Abhängigkeiten mithilfe eines Manifests. Es ist nicht erforderlich, für die Anwendung vollständig isoliert, um ordnungsgemäß unter Windows ausgeführt werden. Sie können jedoch durch eine Investition in Ihre Anwendung isoliert, Zeit sparen, wenn Sie Ihre Anwendung in der Zukunft müssen. Weitere Informationen zu den Vorteilen der wird Ihre Anwendung isoliert, finden Sie unter [isolierte Anwendungen](/windows/desktop/SbsCs/isolated-applications).

Wenn Sie Ihre systemeigene C/C++-Anwendung mit Visual C++ erstellen, generiert Projektsystem standardmäßig der Visual Studio eine manifest-Datei, die die Abhängigkeiten Ihrer Anwendung von Visual C++-Bibliotheken zu beschreiben. Wenn dies die einzigen Abhängigkeiten sind verfügt Ihre Anwendung, wird er einer isolierten Anwendung angezeigt wird, sobald er mit Visual Studio neu erstellt wird. Wenn Ihre Anwendung zur Laufzeit andere Bibliotheken verwendet, müssen Sie möglicherweise diese Bibliotheken als Seite-an-Seite-Assemblys, die anhand der Schritte erneut [Erstellen von C/C++-Seite-an-Seite-Assemblys](building-c-cpp-side-by-side-assemblies.md).

## <a name="see-also"></a>Siehe auch

[Konzept der isolierten Anwendungen und der parallelen Assemblys](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
