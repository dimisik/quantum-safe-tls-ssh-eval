# quantum-safe-tls-ssh-eval
Scripts for evaluating Post-Quantum authentication and key exchange in SSH

## Script Descriptions

**auto_install_ssh**: Automated installation of liboqs and OQS openssh

**loop_ssh_client_control**: Client loop (input =  number of iterations) for ssh establishment - Control group

**loop_ssh_client_x_y**: Client loop (input =  number of iterations) for ssh establishment - x: PQ authentication algorithm, y: PQ key exchange algorithm

**other_procedures_notes_x**: Commands for key generation at server/client (x: PQ authentication algorithm)

**tshark_config_run_ssh**: tshark command for packet capture

**handshake_time_ssh**: Python script to measure ssh handshake time
