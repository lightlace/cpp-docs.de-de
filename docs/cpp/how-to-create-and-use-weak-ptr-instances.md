---
title: "Gewusst wie: Erstellen und Verwenden von weak_ptr-Instanzen | Microsoft Docs"
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
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Gewusst wie: Erstellen und Verwenden von weak_ptr-Instanzen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Manchmal muss ein Objekt eine Möglichkeit speichern, um auf das `shared_ptr` zugrunde liegende Objekt zuzugreifen, ohne dadurch den Referenzzähler zu erhöhen.  Diese Situation tritt in der Regel auf, wenn zyklische Verweise zwischen `shared_ptr`\-Instanzen vorliegen.  
  
 Der optimale Entwurf ist die Vermeidung von gemeinsamem Zeigerbesitz.  Wenn Sie jedoch gemeinsamen Besitz von `shared_ptr`\-Instanzen benötigen, vermeiden Sie zyklische Verweise zwischen ihnen.  Wenn zyklische Verweise unvermeidbar oder aus irgendeinem Grund sogar vorzuziehen sind, verwenden Sie `weak_ptr`, um einem oder mehreren der Besitzer einen schwachen Verweis auf einen anderen `shared_ptr` zu geben.  Mit `weak_ptr` können Sie einen `shared_ptr` erstellen, der eine vorhandene Gruppe verwandter Instanzen verknüpft, wobei nur die zugrunde liegende Speicherressource weiterhin gültig ist.  Der `weak_ptr` selbst nimmt nicht an der Referenzzählung teil und kann daher nicht verhindern, dass der Referenzzähler den Wert 0 erreicht.  Sie können jedoch einen `weak_ptr` verwenden, um zu versuchen, eine neue Kopie des `shared_ptr` zu erhalten, mit der er initialisiert wurde.  Wenn der Arbeitsspeicher bereits gelöscht wurde, wird eine **bad\_weak\_ptr**\-Ausnahme ausgelöst.  Wenn der Arbeitsspeicher noch gültig ist, erhöht der neue freigegebene Zeiger den Verweiszähler und stellt sicher, dass der Arbeitsspeicher gültig bleibt, solange die `shared_ptr`\-Variable im Gültigkeitsbereich liegt.  
  
## Beispiel  
 Das folgende Codebeispiel zeigt einen Fall, in dem `weak_ptr` verwendet wird, um das richtige Löschen von Objekten sicherzustellen, die Ringabhängigkeiten aufweisen.  Nehmen Sie für das Beispiel an, dass es erst erstellt wurde, nachdem keine alternativen Lösungen gefunden werden konnten.  Die `Controller`\-Objekte stellen einige Aspekte eines Computerprozesses dar, und sie funktionieren unabhängig.  Jeder Controller muss in der Lage sein, den Status der anderen Controller jederzeit abzufragen, und jeder enthält zu diesem Zweck einen privaten `vector<weak_ptr<Controller>>`.  Jeder Vektor enthält einen Zirkelverweis. Daher werden `weak_ptr`\-Instanzen anstelle von `shared_ptr` verwendet.  
  
 [!CODE [stl_smart_pointers#222](../CodeSnippet/VS_Snippets_Cpp/stl_smart_pointers#222)]  
  
  **Controller0 wird erstellt**  
**Creating Controller1**  
**Creating Controller2**  
**Creating Controller3**  
**Creating Controller4**  
**push\_back to v\[0\]: 1**  
**push\_back to v\[0\]: 2**  
**push\_back to v\[0\]: 3**  
**push\_back to v\[0\]: 4**  
**push\_back to v\[1\]: 0**  
**push\_back to v\[1\]: 2**  
**push\_back to v\[1\]: 3**  
**push\_back to v\[1\]: 4**  
**push\_back to v\[2\]: 0**  
**push\_back to v\[2\]: 1**  
**push\_back to v\[2\]: 3**  
**push\_back to v\[2\]: 4**  
**push\_back to v\[3\]: 0**  
**push\_back to v\[3\]: 1**  
**push\_back to v\[3\]: 2**  
**push\_back to v\[3\]: 4**  
**push\_back to v\[4\]: 0**  
**push\_back to v\[4\]: 1**  
**push\_back to v\[4\]: 2**  
**push\_back to v\[4\]: 3**  
**use\_count \= 1**  
**Status of 1 \= On**  
**Status of 2 \= On**  
**Status of 3 \= On**  
**Status of 4 \= On**  
**use\_count \= 1**  
**Status of 0 \= On**  
**Status of 2 \= On**  
**Status of 3 \= On**  
**Status of 4 \= On**  
**use\_count \= 1**  
**Status of 0 \= On**  
**Status of 1 \= On**  
**Status of 3 \= On**  
**Status of 4 \= On**  
**use\_count \= 1**  
**Status of 0 \= On**  
**Status of 1 \= On**  
**Status of 2 \= On**  
**Status of 4 \= On**  
**use\_count \= 1**  
**Status of 0 \= On**  
**Status of 1 \= On**  
**Status of 2 \= On**  
**Status of 3 \= On**  
**Destroying Controller0**  
**Destroying Controller1**  
**Destroying Controller2**  
**Destroying Controller3**  
**Destroying Controller4**  
**Press any key** Ändern Sie testweise den Vektor `others` in einen `vector<shared_ptr<Controller>>`, und beachten Sie dann in der Ausgabe, dass keine Destruktoren aufgerufen wurden, als `TestRun` zurückkehrte.  
  
## Siehe auch  
 [Intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md)