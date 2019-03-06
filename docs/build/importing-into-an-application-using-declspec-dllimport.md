---
title: Importieren in eine Anwendung mithilfe von "__declspec(dllimport)"
ms.date: 11/04/2016
f1_keywords:
- __declspec
- dllimport
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
ms.openlocfilehash: ef01c2905dea215a1a52333ae5611ec58c5f5af4
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419217"
---
# <a name="importing-into-an-application-using-declspecdllimport"></a>Importieren in eine Anwendung mithilfe von "__declspec(dllimport)"

Wenn ein Programm öffentliche, durch eine DLL definierte Symbole verwendet, wird dieser Vorgang als Importieren bezeichnet. Bei der Erstellung Headerdateien für Anwendungen, die Ihre DLLs verwenden, erstellen Sie mit dem Sie **von "__declspec(dllimport)" "** für die Deklarationen der öffentlichen Symbole. Das Schlüsselwort **von "__declspec(dllimport)" "** funktioniert, ob der export über DEF-Dateien oder mit der **__declspec(dllexport)** Schlüsselwort.

Um den Code lesbarer gestalten, definieren Sie ein Makro für **von "__declspec(dllimport)" "** und klicken Sie dann das Makro verwenden, um die Deklaration aller importierten Symbole:

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

Mithilfe von **von "__declspec(dllimport)" "** ist bei Funktionsdeklarationen optional, aber der Compiler effizienteren Code generiert, wenn Sie dieses Schlüsselwort verwenden. Sie müssen allerdings verwenden **von "__declspec(dllimport)" "** für die importierende ausführbare Datei, auf die öffentlichen Datensymbole und Objekte der DLLs zugreifen. Beachten Sie, dass die Benutzer Ihrer DLL noch eine Verknüpfung mit einer Importbibliothek herstellen müssen.

Sie können dieselbe Headerdatei sowohl für die DLL als auch für die Clientanwendung nutzen. Verwenden Sie zu diesem Zweck ein spezielles Präprozessorsymbol, das angibt, ob die DLL oder die Clientanwendung erstellt wird. Zum Beispiel:

```
#ifdef _EXPORTING
   #define CLASS_DECLSPEC    __declspec(dllexport)
#else
   #define CLASS_DECLSPEC    __declspec(dllimport)
#endif

class CLASS_DECLSPEC CExampleA : public CObject
{ ... class definition ... };
```

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)

- [Gegenseitige Importe](../build/mutual-imports.md)

## <a name="see-also"></a>Siehe auch

[Importieren in eine Anwendung](../build/importing-into-an-application.md)
