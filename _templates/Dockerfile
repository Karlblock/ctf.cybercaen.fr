FROM ubuntu:22.04

# Installer les dépendances
RUN apt-get update && apt-get install -y \
    openssh-server \
    && rm -rf /var/lib/apt/lists/*

# Créer l'utilisateur du challenge
RUN useradd -m -s /bin/bash ctf && echo "ctf:ctf" | chpasswd

# Copier les fichiers du challenge
COPY files/ /home/ctf/

# Configuration SSH
RUN mkdir /run/sshd
EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
