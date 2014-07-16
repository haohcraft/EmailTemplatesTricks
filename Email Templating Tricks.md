Email Templating Tricks


1. Spacing & padding (Nest Tables for Consistent Spacing)
	- add this to text/css to avoid the mysterious spacing

			table { border-collapse:collapse; mso-table-lspace:0pt; mso-table-rspace:0pt; } 
			<!-- horizontal spacing -->
			<table width="10" align="left" cellpadding="0" cellspacing="0"  border="0" style="width=10px;">
				<tbody>
					<tr>
						<td width="10" height="10"  style="width:10px;height:10px;">&nbsp;</td>
					</tr>
				</tbody>
			</table>
			<!-- vertical spacing -->
			<tr>
				<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
			</tr>

2. Make columns
	- sample codes:

			tr
				table class="theTotalWidth(15+300+15)" cellpadding="0" cellspacing="0" border="0"
					tbody 
						tr
							<td class="w15" width="15" valign="top"></td>
							<td class="w300" width="300" valign="top"></td>
							<td class="w15" width="15" valign="top"></td>

3. Set widths in each cell rather than on the table

	<table cellspacing="0" cellpadding="0" border="0">
	  <tr>
	    <td width="150"></td>
	    <td width="350"></td>
	  </tr>
	</table>

4. Set a Background Color on a Container Table

5. Use alt attributes when there is a image

6. Some common issues
	- iOS creates blue links over dates and addresses
	
			span[class="ios-link"] a {
			  color: #117692;
			  text-decoration: underline;
			}

7. outlook browser client makes blue links
	
		<a>
			<span style="text-decoration:none;">laal</span>

8. image 

	Images are well support as long as they are put into the template with <img> tags.

	- Always add `style="display:block"` to images. Without this rule gmail will add phantom space below the image in the online reader
	- Always add `border="0"` to `<img>` tags otherwise there will be a border around your images
	- Background images via the style attribute are not widely supported and should not be used

9. Hide the mobile content on destop
	- Reference 1:  [How to hide mobile content in destop](https://www.campaignmonitor.com/forums/topic/7405/how-to-hide-mobile-content-in-desktop-clients/)
	- Reference 2:  [Hiding Content in Both Desktop and Web Email Clients](https://www.campaignmonitor.com/blog/post/3948/hiding-content-in-both-desktop-and-web-email-clients)

	In summary:

		@media only screen and (max-device-width: 480px) {

				*[class=mobileHide] { 
					display:none !important;
					font-size: 0 !important;
					max-height:0 !important;
					font-size: 0 !important;
					line-height: 0 !important;

				}
				*[class=mobileShow] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1.5 !important;

				}

				*[class=mobileShow-13] { 
					display:block !important;
					font-size: 13px !important; //reset the font-size
					max-height:none !important;
					line-height: 1.5 !important;


				}
			}
	AND for `mobileHide`, just put regular inline styles
	But for `mobileShow-*`, should put inline styles:  

			display:none;font-size: 0; max-height: 0; line-height: 0;

	Should not only hide <tr> but also <td> as well:

			<!-- vertical spacing -->
				<tr class="mobileShow-h5-topborder" style="display:none; font-size: 0px; max-height: 0; line-height: 0; mso-hide: all;">
					<td class="mobileShow-h5-topborder" style="display:none; font-size: 0px; max-height: 0; line-height: 0; mso-hide: all;"></td>
				</tr>

10. Show/hide images
	
		<div class="mobileHide">
			<img class="mobileHide" src=$image_basic_url/DesktopA_SearchWidget.png  alt="" class="" width="700" height="90" border="0" style="display:block; width:700px; height: 90px;">
		</div>
		<div class="mobileShow-image-w480" style="display:none; height: 90px; max-height: 0; width:0px; mso-hide: all;"> 
			<img class="mobileShow-image-w480" src=$image_basic_url/MobileA_SearchWidget.png  alt="" class="" width="0" border="0" style="display:block; width:0; height: 90px; mso-hide: all;">
		</div>

11. To hide the content in the Outlook Web App

	Add `font: 0;` in the `<tr>`
	NOTE: there is no "font-size: 0px" in `<tr>` but only in `<td>`

		<tr class="mobileShow-f13" style="display:none; font:0; height:0px; max-height: 0; line-height: 0; mso-hide: all;">
			<td class="mobileShow-f13-left" align="left" style="font-family: $font-family; color: $font-color-black; display:none; font-size: 0px;height:0px; max-height: 0; line-height: 0; mso-hide: all;">
				Round trip
			</td>
		</tr>

12. When there are two tables under the td, we *SHOULD* set a *LARGE* enough "height" value to that <td> 

13. When try to lay two tables next to each other horizontall, *SHOULD* specify the width of them

14. For Gmail APP on Android, we need to add a dummy padding at the end of the table to stretch the view to show correctly

		<tr>
		<td class="mobilehide">
			<table class="mobilehide" cellspacing="0" cellpadding="0" border="0" align="center" width="700">
				<tr>
					 <td class="mobilehide nopadding" style="padding:0 350px">&nbsp;</td>>
				</tr>
			</table>
		</td>
		</tr>

15. To show the black right arrow emoji, we *should* choose `&#9656;` instead of `&#9654;` or `&#9658;` in order to avoid Apple Emoji

		