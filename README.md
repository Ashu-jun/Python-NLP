# READING PDF FILES 
"""
    This Application parse multiple pdf files present in a given directory ,extract images
    and text place it in new directory separately
"""


import os
from ExtractImages import extractImages
from ReadText import readText


# function to get list of existing pdf files in the given directory 'dirName'
def getList(dirName):
    file_names = []

    for file in os.listdir(dirName):
        if file.endswith(".pdf"):
            file_names.append(file)
    return file_names


# getAll makes new directory for each pdf file and stores images and text there
def getAll(dirName):
    file_names = getList(dirName)
    # extract images for every file in the directory
    for x in file_names:
        extractImages(x)
        readText(x)




