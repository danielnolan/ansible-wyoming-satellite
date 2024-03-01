Wyoming Satellite
=========

 This is an ansible role for building a wyoming satellite based on this
 tutorial https://github.com/rhasspy/wyoming-satellite/blob/master/docs/tutorial_2mic.md

Requirements
------------

A built wyoming satellite with the two mic hat.

Role Variables
--------------
These are the variables. These can be overridden using group or host
vars or passed in from your playbook when using this role.
```yaml
mic_auto_gain: 4
mic_command: "arecord -D plughw:CARD=seeed2micvoicec,DEV=0 -r 16000 -c 1 -f S16_LE -t raw"
mic_noise_suppression: 2
satellite_name: Wyoming Satellite
snd_command: "aplay -D plughw:CARD=seeed2micvoicec,DEV=0 -r 22050 -c 1 -f S16_LE -t raw"
user: "{{ ansible_user_id }}"
wyoming_openwakeword_dir: "/home/{{ user }}/wyoming-openwakeword"
wyoming_satellite_dir: "/home/{{ user }}/wyoming-satellite"
wake_word: "hey jarvis"
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: satellites
      roles:
         - { role: whyoming-satelltie, mic_auto_gain: 5 }

License
-------

BSD

Author Information
------------------

Daniel Nolan danielanolan@gmail.com
