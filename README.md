# Image-Similarity-Index
SURF:

SURF approximates the DoG with box filters. Instead of
Gaussian averaging the image, squares are used for
approximation since the convolution with square is much
faster if the integral image is used. Also this can be done in
parallel for different scales. The SURF uses a BLOB detector
which is based on the Hessian matrix to find the points of
interest. For orientation assignment, it uses wavelet responses
in both horizontal and vertical directions by applying adequate
Gaussian weights. For feature description also SURF uses the
wavelet responses. A neighborhood around the key point is
selected and divided into subregions and then for each
subregion the wavelet responses are taken and represented to
get SURF feature descriptor. The sign of Laplacian which is
already computed in the detection is used for underlying
interest points. The sign of the Laplacian distinguishes bright
blobs on dark backgrounds from the reverse case. In case of
matching the features are compared only if they have same
type of contrast (based on sign) which allows faster matching .

ORB :

ORB is a fusion of the FAST key point detector and BRIEF
descriptor with some modifications [9]. Initially to determine
the key points, it uses FAST. Then a Harris corner measure is
applied to find top N points. FAST does not compute the
orientation and is rotation variant. It computes the intensity
weighted centroid of the patch with located corner at center.
The direction of the vector from this corner point to centroid
gives the orientation. Moments are computed to improve the
rotation invariance. The descriptor BRIEF poorly per forms if
there is an in-plane rotation. In ORB, a rotation matrix is
computed using the orientation of patch and then the BRIEF
descriptors are steered according to the orientation.
