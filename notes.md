Do zrobienia

Omówić róznice między:
  * `pip install package_name`, - instalacja z pypi.org
  * `pip install path/to/package` - instalacja z katalogu
  * `pip install -e path/to/package` - instalacja w trybie edytowalnym
  * `pip install git+url_of_git_repository.git` - instalacja z repozytorium (z domyslnej gałęzi)
  * `pip install git+url_of_git_repository.git@branch_name` - instalacja z repozytorium (z domyslnej gałezi `branch_name`)
    
Czemu warto zrobić kod instalowalny jako biblioteka:
  * łatwe dzielenie między projektami
  * łatwiejsze użycie kodu przez innych

`setup.py` 

`setup.cfg` - przechowywanie statycznych metadanych. 
Mogą go wykorzystywać inne narzędzia do przechowywania swoich ustawień (np. pytest https://github.com/4DNucleome/PartSeg/blob/5e50b7500cfd95022b22e428b6f11de6ac791017/setup.cfg#L98)
Pozwala zachować kod setup.py czystym.

https://www.python.org/dev/peps/pep-0390/ - odrzucony, bo nie jest implementowany w bibliotece standardowej tylko w bibiliotece setuptools:
https://setuptools.readthedocs.io/en/latest/userguide/declarative_config.html?highlight=setup.cfg


`pyproject.toml` 
Powstał aby objestć pewne ograniczenia distutils/setuptools (setup.py/setup.cfg)
https://www.python.org/dev/peps/pep-0517/
Pozwala wyspecyfikować biblioteki potrzebne w czasie budowania pakietu (główne ograniczenie distutils/setuptools) i 
wybrać metode budowania pakietu. Jest to najczęsciej `setuptools.build_meta`, ale są też inne opcje. Szczególnie dla rozszerzeń 
binarnych pisanych w językach spoza rodziny C/C++.
`

Pozwala również trzymać ustawienia zewnętrzynch narzędzi. 
https://github.com/4DNucleome/PartSeg/blob/5e50b7500cfd95022b22e428b6f11de6ac791017/pyproject.toml#L9