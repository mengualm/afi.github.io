
# Guía de Instalación de Volatility 3 en Kali Linux

Esta guía te ayudará a instalar **Volatility 3** en Kali Linux sin interferir con una instalación existente de **Volatility 2**.

---

## 🧩 Requisitos Previos
- Tener Volatility 2 instalado con Python 2.7
- Tener acceso a terminal con privilegios de sudo

---

## 🛠️ Paso 1: Instalar dependencias para Python 3

```bash
sudo apt update
sudo apt install -y python3 python3-dev python3-pip python3-setuptools python3-wheel git
```

---

## 📥 Paso 2: Clonar el repositorio de Volatility 3

```bash
git clone https://github.com/volatilityfoundation/volatility3.git
cd volatility3
```

---

## 📦 Paso 3: Instalar las dependencias de Volatility 3

```bash
pip3 install -r requirements.txt
```

---

## ✅ Paso 4: Verificar la instalación

```bash
python3 vol.py -h
```

Deberías ver el menú de ayuda de Volatility 3.

---

## 🧠 Usar Volatility 2 y 3 sin conflictos

Mantén ambos repositorios en carpetas separadas, por ejemplo:

```bash
~/herramientas/volatility2/
~/herramientas/volatility3/
```

### Crear alias para facilitar el uso:

Edita tu archivo `.bashrc`:

```bash
echo "alias vol2='python2 ~/herramientas/volatility2/vol.py'" >> ~/.bashrc
echo "alias vol3='python3 ~/herramientas/volatility3/vol.py'" >> ~/.bashrc
source ~/.bashrc
```

Ahora puedes ejecutar:

```bash
vol2 --info
vol3 -h
```

---

## 📄 Recursos
- [Repositorio Volatility 3](https://github.com/volatilityfoundation/volatility3)
- [Documentación oficial](https://volatility3.org/)

