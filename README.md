![Build Status](https://api.travis-ci.com/Townk/ansible-beautiful-output.svg?branch=master)

# Beautiful Output
This role ships with a callback plugin to allow you to display the execution of
your playbook on a very beautiful way (in my opinion.)

![Screenshot](https://raw.githubusercontent.com/Townk/ansible-beautiful-output/master/meta/screenshot.png "Standard output for the beautiful output callback plugin")

I was always obsessed about the looks of my terminal, and when I started using
Ansible, there was no Callback available that looked good enough for my taste.
Faced with such scenario, I spent some time to create this plugin to satisfy my
_"beautiful terminal"_ goal with Ansible.

Is worth notice that taste is a very subjective point, and what looks good for
me is not necessarilly good for you.

## Requirements
The control machine has to have the `watchdog` python libraries installed prior
of running your playbook with this callback setup.

You can install it using pip:

```sh
$ pip install watchdog
```

Or add it to your `requirements.txt` file.

## Dependencies
No dependency to any other Role.

## How to use it
First let Ansible know that you will use the plugin as an stdout pluguin on your
`ansible.cfg` file:

```ini
[defaults]
# Use the Beautiful Output callback plugin.
stdout_callback = beautiful_output
# Use the stdout_callback when running ad-hoc commands.
bin_ansible_callbacks = True
```

Than, for each playbook you want running with this callback plugin, add the
role on the playbook file:

```yaml
    - hosts: servers
      roles:
         - role: townk.beautiful_output
```

## Screenshots

### Failure
![Screenshot](https://raw.githubusercontent.com/Townk/ansible-beautiful-output/master/meta/screenshot_failure.png "Failed output for the beautiful output callback plugin")

### Detail of a verbose failure
![Screenshot](https://raw.githubusercontent.com/Townk/ansible-beautiful-output/master/meta/screenshot_failure_verbose.png "Details on failure when using the options -vvv")

## License

MIT License

Copyright (c) 2019 Thiago Alves

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## About the author
My real name is Thiago Alves and I'm an old-school software engineer trying to
keep up with the cool kids' toys of these days.
