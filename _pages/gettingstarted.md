---
title: "Getting Started"
layout: textlay
excerpt: "How to set up, upload and manage your data on DANDI archive"
sitemap: false
permalink: /gettingstarted
---

## Setting up

<br>

### Web

#### 1. [Create a Github account](https://www.github.com) if you don't have one.
#### 2. Login to the [DANDI Archive data portal](https://gui.dandiarchive.org/) with your Github Account (click Login).
	
	ADD PICTURE


*Currently new sign-ins will need to be approved by us, but you will get an email after your account is approved.*

#### 3. After logging in, retrieve your API key (this is under your user initials after logging in).

	ADD PICTURE


<br>

### Locally

#### 1. Create a Python environment on your local computer (e.g., Miniconda, virtualenv).
#### 2. Install the [DANDI client](https://github.com/dandi/dandi-cli) into your Python environment with `pip install dandi`

<br>

---

<br>

## Data upload & management workflow 

Note that this project is under heavy development.  Check the [`dandi-cli`](https://github.com/dandi/dandi-cli) and 
the [`dandi-archive`](https://github.com/dandi/dandiarchive) repos for updates on the command line tool and webpage.

<br>

#### 1. Register a dandiset to generate an identifier

You can use either of the two methods. For each you will be asked to enter basic metadata, a name (title) and description (abstract) for your dataset.

- **Web** 

	Click NEW DATASET after logging in

		ADD PICTURE


- **Terminal** 

	Run `dandi register`.  You will be asked for your API key.


		ADD PICTURE




<br>


#### 2. Convert your data to the NWB 2.1+ format in a local folder

Feel free to reach out to us for help with us.  Let's call the folder containing the files `source_folder`

	ADD PICTURE

<br>


#### 3. Use the `dandi` cli to validate, organize and upload your data

Refer to the github README and the `--help` flag for more details on each command

You can also a look at this [example script](https://github.com/dandi/dandi-cli/blob/master/doc/demos/basic-workflow1.sh) that does everything in this step (assuming no changes are necessary).



- `dandi validate` to verify that files conform NWB schema and DANDI requirement


	*If necessary, adjust your conversion scripts or use helper utilities to address concerns identified by the `dandi validate` command then run it again*


		ADD PICTURE


- Use `dandi organize` to upload your data  

		dandi organize <source_folder> -f dry
		dandi organize <source_folder> -f symlink
		ADD PICTURE


	Validate your data again just to be safe

		ADD PICTURE


- `dandi upload` to upload your data  

		ADD PICTURE


<br>



#### 4. Add & edit metadata on the Web

Click on the pen edit icon by visiting your dandiset landing page `https://dandiarchive.org/<dataset_id>/draft`


	ADD PICTURE

<br>

---

<br>

## Data Download

Use `dandi download <dandiset_url>` to download any dataset from the terminal.

iv. Downloading a dataset from the archive with `dandi download https://dandiarchive.org/<dataset_id>/draft`


ADD PICTURE

Add url issues

*in your preprint*


<br>

---


### Work in Progress

- Publish dandiset with versions (coming soon)
- Add collaborators to your dandiset (right now, ask us)
- Allow multiple people to make changes (right now, coordinate with your collaborators)

<br>

### Where to communicate

- For general discussion post on [Neurostars](https://neurostars.org)
- Report bugs at our [github issues page](https://github.com/dandi/dandiarchive/issues)
- Register on DANDI and we will invite you to the DANDI Slack workspace
- Email us at info@dandiarchive.org  
